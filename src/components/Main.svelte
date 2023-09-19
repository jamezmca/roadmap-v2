<script>
    import store from "../store";
    import Roadmap from "./Roadmap.svelte";
    let name = "";

    let styles;

    $: {
        let darkTheme = $store.darkTheme;

        styles = {
            inputColor: darkTheme ? " bg-slate-950" : " bg-white",
            accentColor: darkTheme ? " text-blue-400" : " text-blue-500",
            fadedColor: darkTheme ? " text-slate-200 " : " text-slate-500",
            blueText: darkTheme ? " text-blue-400" : " text-blue-500",
            amberText: darkTheme ? " text-amber-400" : " text-amber-500",
        };
    }

    function handleSaveName() {
        if (!name) {
            return;
        }
        $store.name = name;
    }

    const onKeyPress = (e) => {
        if (e.charCode === 13) {
            handleSaveName();
        }
    };
</script>

<main
    class="flex-1 p-4 max-w-[1000px] mx-auto w-full flex flex-col min-h-[400px] sm:min-h-[500px]"
>
    <div
        class={" flex-col justify-center items-center flex-1 gap-6 max-w-[600px] w-full mx-auto pb-10 pt-20 " +
            (!$store.name ? " flex" : " hidden")}
    >
        <h1 class="text-3xl sm:text-4xl md:text-5xl font-semibold text-center">
            Welcome to the Webdev
            <span class={" " + styles.accentColor}>Roadmap</span>
        </h1>

        <h4 class=" text-center">
            <span class=" font-semibold">Level up</span> your programming skills
            from
            <span class={"font-semibold " + styles.blueText}>zero</span>
            to
            <span class={"font-semibold " + styles.amberText}>hero</span>!
        </h4>

        <!-- <p class={"italic " + styles.fadedColor}>- by Smoljames</p> -->
        <div class="flex gap-1 text-xs sm:text-sm">
            <h4>4.55</h4>
            <div class="flex items-center gap-0.5 text-xs">
                {#each [1, 2, 3, 4, 5] as ratingNum}
                    <div class="grid place-items-center relative">
                        {#if ratingNum == 5}
                            <div
                                class="flex justify-end w-[45%] absolute top-1/2 -translate-y-1/2 right-0 overflow-hidden"
                            >
                                <i class="fa-solid fa-star text-white" />
                            </div>
                        {/if}
                        <i class="fa-solid fa-star text-amber-400" />
                    </div>
                {/each}
            </div>
            <h4>(200+)</h4>
        </div>
        <div class="flex p-0.5 w-full relative">
            <div
                class="absolute inset-0 overflow-hidden rounded-md flex items-center justify-center"
            >
                <div
                    class="bg-gradient-to-r w-[200%] aspect-square from-blue-600 to-cyan-300 specialSpin"
                />
            </div>

            <div class={"flex flex-1 rounded  relative " + styles.inputColor}>
                <input
                    on:keypress={onKeyPress}
                    bind:value={name}
                    class="rounded-md flex-1 outline-none hover:outline-none bg-transparent p-3"
                    placeholder="Enter name to begin"
                />
                <button
                    on:click={handleSaveName}
                    class={" py-2 rounded-md  hover:opacity-60 px-3 duration-200   " +
                        styles.buttonBackground +
                        " " +
                        (name
                            ? " text-cyan-400 scale-[105%] sm:scale-110"
                            : " ")}
                >
                    <i class="fa-solid fa-arrow-right" />
                </button>
            </div>
        </div>

        <!-- <p class="text-sm opacity-80">
                Input your name and hit <span class="font-semibold">Enter</span>
                to begin
            </p> -->
    </div>
    <Roadmap />
</main>
