<script>
    import { onMount } from "svelte";
    import store from "../store";
    let email = "";
    let emailStatus = "";
    let error = false;
    let rating = null;
    let chosenRating = null;

    let styles;

    onMount(() => {
        if (localStorage.getItem("roadmapRating")) {
            chosenRating = parseInt(localStorage.getItem("roadmapRating"));
        }
    });

    $: {
        let darkTheme = $store.darkTheme;
        styles = {
            inputColor: darkTheme
                ? " bg-transparent border-blue-950 focus-within:border-blue-900 hover:border-blue-900"
                : " bg-transparent border-blue-100 focus-within:border-blue-300 hover:border-blue-300",
            starColor: (ratingNum) =>
                ratingNum > (chosenRating || rating)
                    ? darkTheme
                        ? " text-white"
                        : " text-slate-600"
                    : " text-amber-300",
        };
    }

    async function handleSubscribe() {
        if (!email || emailStatus !== "") {
            return;
        }

        emailStatus = "sending";
        try {
            const res = await fetch(
                "https://mailing-list-3hzb.onrender.com/api/register",
                {
                    method: "POST",
                    headers: {
                        "Content-type": "application/json",
                    },
                    body: JSON.stringify({
                        password: "80085",
                        email,
                        platform: "course",
                    }),
                }
            );
            if (res.status === "201") {
                console.log("Sent");
            }
            emailStatus = "sent";
            email = "";
        } catch (err) {
            console.log("Failed to subscribe");
            emailStatus = "";
        }
    }

    const onKeyPress = (e) => {
        if (e.charCode === 13) {
            handleSubscribe();
        }
    };

    async function handleRating() {
        if (!rating || chosenRating) {
            return;
        }

        console.log(rating);
        chosenRating = rating;

        try {
            const res = await fetch(
                // "http://localhost:5353/api/rate",
                "https://mailing-list-3hzb.onrender.com/api/rate",
                {
                    method: "POST",
                    headers: {
                        "Content-type": "application/json",
                    },
                    body: JSON.stringify({
                        password: "80085",
                        rating: rating,
                        platform: "roadmap",
                    }),
                }
            );
            localStorage.setItem("roadmapRating", chosenRating);
            if (res.status === "201") {
                console.log("Sent");
            }
        } catch (err) {
            console.log("Failed to leave review");
        }
    }
</script>

<footer
    class="py-14 md:py-20 flex flex-col gap-10 md:gap-14 items-center justify-center p-4 text-sm"
>
    {#if $store.name}
        <div class="flex flex-col gap-4">
            <h4 class="text-center">Enjoying the guide? Leave a review!</h4>
            <div class="flex items-center justify-center">
                {#each [1, 2, 3, 4, 5] as ratingNum}
                    <button
                        on:click={handleRating}
                        on:mouseenter={() => (rating = ratingNum)}
                        on:mouseleave={() => (rating = null)}
                        class={"grid place-items-center text-2xl sm:text-3xl px-1.5 sm:px-2 " +
                            styles.starColor(ratingNum)}
                    >
                        <i class="fa-solid fa-star" />
                    </button>
                {/each}
            </div>
        </div>
    {/if}

    <div class="flex flex-col gap-4">
        <h4 class="text-center">
            Interested in a <span class="text-blue-400">Web Development</span> course
            - join the mailing list!
        </h4>
        <a
            href="https://smoljames.beehiiv.com/subscribe"
            target="_blank"
            class="mx-auto p-2 px-4 hover:border-blue-600 duration-200 rounded-md border border-blue-400"
            ><h4>Subscribe here &rarr;</h4></a
        >
        <!-- <div
            class={"flex mx-auto w-full max-w-96 border border-solid  duration-200 rounded overflow-hidden " +
                styles.inputColor}
        >
            <input
                on:keypress={onKeyPress}
                class="flex-1 p-2 outline-none focus:outline-none bg-transparent"
                placeholder="Email"
                bind:value={email}
            />
            <button
                on:click={handleSubscribe}
                class="grid place-items-center relative"
            >
                <i
                    class={"fa-regular fa-envelope px-3 cursor-pointer hover:text-blue-400 duration-200 " +
                        (emailStatus != "" ? " opacity-0" : " opacity-100")}
                />
                {#if emailStatus === "sending"}
                    <div class="absolute inset-0 grid place-items-center">
                        <i class="fa-solid fa-spinner animate-spin" />
                    </div>
                {:else if emailStatus === "sent"}
                    <div class="absolute inset-0 grid place-items-center">
                        <i class="fa-solid fa-check text-green-400" />
                    </div>
                {/if}
            </button>
        </div> -->
    </div>
    <!-- <div class="flex flex-col gap-4">
        <h4 class="text-center">The brand new Smoljames Store </h4>
    </div> -->
    <div class="flex flex-col gap-4 text-center">
        <h4 class="">Join the Guild</h4>

        <div
            class="flex gap-4 items-center flex-wrap justify-center text-2xl sm:text-3xl"
        >
            <a
                href={"https://github.com/jamezmca"}
                target="_blank"
                class="hover:text-blue-400 duration-200"
            >
                <i class="fa-brands fa-github" />
            </a>
            <a
                href={"https://youtube.com/smoljames"}
                target="_blank"
                class="hover:text-blue-400 duration-200"
            >
                <i class="fa-brands fa-youtube" />
            </a>
            <a
                class="hover:text-blue-400 duration-200"
                href={"https://www.linkedin.com/in/jamezmcarthur/"}
                target="_blank"
            >
                <i class="fa-brands fa-linkedin" />
            </a>
            <a
                href={"https://discord.gg/BYr6gujs4k"}
                target="_blank"
                class="hover:text-blue-400 duration-200"
            >
                <i class="fa-brands fa-discord" />
            </a>
        </div>
    </div>
    <div class="flex flex-row items-center gap-2 text-sx sm:text-sm">
        <a
            href="https://www.smoljames.com"
            class="flex items-center gap-2"
            target="_blank"
        >
            <i class="fa-solid fa-house" />
            <h4><span class="text-blue-400">Smoljames Hub</span></h4>
        </a>
        <p class="">|</p>
        <a
            href="https://www.store.smoljames.com"
            class="flex items-center gap-2"
            target="_blank"
        >
            <h4>
                <span class="text-blue-400"> Smoljames Store</span>
            </h4>
            <i class="fa-solid fa-store" />
        </a>
    </div>
</footer>
