<script>
    import "../app.css";
    import store, { defaultObj } from "../store";
    import Footer from "../components/Footer.svelte";
    import Header from "../components/Header.svelte";
    import { onMount } from "svelte";
    let y;

    function goTop() {
        document.body.scrollIntoView();
    }

    let styles;

    $: {
        let darkTheme = $store.darkTheme;
        styles = {
            arrowColors: darkTheme
                ? " bg-slate-950 text-blue-400"
                : " bg-slate-200 text-slate-600",
        };
    }

    onMount(() => {
        try {
            if (localStorage.getItem("codemap")) {
                const previousProgress = JSON.parse(
                    localStorage.getItem("codemap")
                ).progress;
                for (let chapter in previousProgress) {
                    for (let milestone of previousProgress[chapter]) {
                        if (
                            chapter in $store.roadmap &&
                            milestone in
                                ($store.roadmap?.[chapter]?.milestones || {})
                        ) {
                            $store.roadmap[chapter].milestones[
                                milestone
                            ].complete = true;
                        }
                    }
                }
                localStorage.removeItem("codemap");
            }
        } catch (err) {
            console.log("Failed to read from old roadmap");
        }

        try {
            if (defaultObj["version"] !== $store?.version) {
                console.log("Updating to version ", defaultObj["version"]);
                let newState = {
                    ...defaultObj,
                    darkTheme: $store.darkTheme,
                    name: $store.name,
                    version: defaultObj["version"],
                };

                for (let chapter in $store.roadmap) {
                    if (!(chapter in newState.roadmap)) {
                        continue;
                    }
                    for (let milestone in $store.roadmap[chapter].milestones) {
                        if (
                            !(milestone in newState.roadmap[chapter].milestones)
                        ) {
                            continue;
                        }

                        newState.roadmap[chapter].milestones[
                            milestone
                        ].complete =
                            $store.roadmap[chapter].milestones[
                                milestone
                            ].complete;
                    }
                }
                $store = { ...newState };
                console.log("Finished update");
            }
        } catch (err) {
            console.log("Failed to complete updates");
        }
    });
</script>

<div
    class={"bodyContainer min-h-screen flex flex-col relative  duration-200 text-sm sm:text-base " +
        ($store.darkTheme
            ? " from-slate-950 to-slate-800 text-white "
            : " from-blue-50 to-white text-slate-700")}
>
    <div
        class={"fixed top-0 left-0 w-full h-full z-[-1] bg-gradient-to-b " +
            ($store.darkTheme
                ? " from-slate-950 to-slate-900  "
                : " from-blue-50 to-white ")}
    />
    <Header />
    <slot />
    <Footer />

    <button
        on:click={goTop}
        class={"grid place-items-center w-8 sm:w-10 duration-200 z-[10] fixed bottom-4 right-4 aspect-square rounded-full " +
            (y === 0
                ? " pointer-events-none opacity-0 "
                : " opacity-100 cursor-pointer ") +
            styles.arrowColors}
    >
        <i class="fa-solid fa-arrow-up" />
    </button>
    <!-- <div
        class={"w-full max-w-[1000px] pointer-events-none fixed bottom-4 pr-4 z-50 flex items-center justify-end right-1/2 translate-x-1/2 duration-200 "}
    >
        <button
            on:click={goTop}
            class={"grid place-items-center w-8 sm:w-10 aspect-square rounded-full " +
                (y === 0
                    ? " pointer-events-none opacity-0 "
                    : " opacity-100 cursor-pointer ") +
                styles.arrowColors}
        >
            <i class="fa-solid fa-arrow-up" />
        </button>
    </div> -->
</div>

<svelte:window bind:scrollY={y} />


