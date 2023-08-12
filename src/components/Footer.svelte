<script>
    import store from "../store";
    let email = "";
    let emailStatus = "";
    let error = false;

    let styles;

    $: {
        let darkTheme = $store.darkTheme;
        styles = {
            inputColor: darkTheme
                ? " bg-transparent border-blue-950 focus-within:border-blue-900 hover:border-blue-900"
                : " bg-transparent border-blue-100 focus-within:border-blue-300 hover:border-blue-300",
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
</script>

<footer
    class="py-10 sm:py-14 md:py-20 flex flex-col gap-4 sm:gap-6 md:gap-8 items-center justify-center p-4 text-sm"
>
    <div class="flex flex-col gap-4">
        <h4 class="text-center">
            Interested in a <span class="text-blue-400">Web Dev</span> course - join
            the mailing list!
        </h4>
        <div
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
        </div>
    </div>
    <div class="flex flex-col gap-4">
        <h4 class="text-center">Join the Guild</h4>
        <div class="flex gap-4 items-center flex-wrap justify-center text-3xl">
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
    <a
        href="https://www.smoljames.com"
        class="flex items-center gap-2"
        target="_blank"
    >
        <i class="fa-solid fa-house" />
        <h4>Back to <span class="text-blue-400">Smoljames.com</span></h4>
    </a>
</footer>
