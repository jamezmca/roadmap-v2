<script>
    import store from "../store";

    function toggleTheme() {
        $store.darkTheme = !$store.darkTheme;
    }

    let styles;

    $: {
        let darkTheme = $store.darkTheme;
        styles = {
            accentColor: darkTheme ? " text-blue-400" : " text-blue-500",
            fadedColor: darkTheme ? " text-slate-300 " : " text-slate-500",
            specialShadow: darkTheme
                ? " specialLightShadow"
                : " specialDarkShadow",
            toggleColor: darkTheme
                ? " border-transparent hover:border-slate-600 "
                : " border-transparent hover:border-slate-300",
            menuColor: darkTheme
                ? " bg-slate-900 border-slate-950"
                : " bg-white border-blue-50 ",
            progressBarColor: darkTheme ? " bg-slate-600" : " bg-slate-300",
            iconColor: darkTheme ? " text-blue-400" : " text-amber-400",
        };
    }

    let count;

    $: {
        let tempCount = 0;
        for (let chapter in $store.roadmap) {
            for (let milestone in $store.roadmap[chapter].milestones) {
                if ($store.roadmap[chapter].milestones[milestone].complete) {
                    tempCount++;
                }
            }
        }
        count = tempCount;
    }
</script>

<section
    class="border-b border-solid border-slate-400 text-xs sm:text-sm  p-4 flex items-center justify-center text-center"
>
    <a
        class=""
        href="/Webdev Roadmap Certificate - track progress & sign on completion.jpg"
        download
    >
        <h4>
            Download the <span class="text-blue-400">Webdev Roadmap</span> mobile
            wallpaper &rarr;
        </h4>
    </a>
</section>
<header class=" flex items-center justify-between p-4 gap-2 relative">
   
    <a href="/" class="flex flex-col text-center">
        <div class="flex items-center gap-2">
            <img
                class="w-10 sm:w-12 md:w-14 hidden sm:inline"
                src="/pc.png"
                alt="logo_img"
            />
            <div class="flex flex-col gap-1">

                <h1 class="font-medium ">
                    Webdev <span class={"poppins " + styles.accentColor}
                    >Roadmap</span
                    >
                </h1>
              
            </div>
        </div>
        <!-- <h3 class={"text-xs sm:text-sm italic" + fadedColor}>Guide by Smoljames</h3> -->
    </a>
    <div
        class="flex items-center gap-3 sm:gap-5 md:gap-6 text-base sm:text-lg md:text-xl"
    >
        <button
            on:click={toggleTheme}
            class={"grid place-items-center  duration-200 hover:opacity-60"}
        >
            {#if $store.darkTheme}
                <i class={"fa-regular fa-sun "} />
            {:else}
                <i class={"fa-regular fa-moon "} />
            {/if}
        </button>
        <!-- <a href="https://www.youtube.com/smoljames" target="_blank" class="duration-200 hover:opacity-60">
            <i class="fa-brands fa-youtube"></i>
        </a> -->
        <a
            href="https://discord.gg/BYr6gujs4k"
            target="_blank"
            class="duration-200 hover:opacity-60"
        >
            <i class="fa-brands fa-discord" />
        </a>
        <a
            href="https://store.smoljames.com"
            target="_blank"
            class="duration-200 hover:opacity-60"
        >
        <i class="fa-solid fa-store"></i>
        </a>
        <!-- <div class="flex items-stretch gap-1 relative">
            <h6 class="text-xs z-1 ">Prog<br/>ress</h6>
            <div class={"relative  w-2  my-0.5 " + styles.progressBarColor}>
                <div
                    class="w-full absolute bottom-0 left-0 bg-emerald-400"
                    style={`height: ${(count * 100) / 20}%;`}
                />
            </div>
        </div> -->
        <div class="flex items-centerrelative">
     
            <div class={"relative h-6 sm:h-7 w-2 " + styles.progressBarColor}>
                <div
                    class="w-full absolute bottom-0 left-0 bg-emerald-400"
                    style={`height: ${(count * 100) / 22}%;`}
                />
            </div>
        </div>
        <!-- <div
            class={"grid place-items-center duration-200 relative group "}
        >
            <i
                class="fa-regular fa-user duration-200 group-hover:opacity-60 cursor-pointer"
            />
            <div
                class="flex-col absolute top-full right-0 pt-1 hidden group-hover:flex"
            >
                <div
                    class={"flex flex-col w-48 sm:w-56 gap-3 p-2 rounded-md shadow border border-solid " +
                        styles.menuColor}
                >
                    <div class="flex items-center justify-between gap-2">
                        <i class="fa-regular fa-user" />
                        <h4 class="text-sm truncate">
                            {$store.name || "New user"}
                        </h4>
                    </div>
                    <div class="flex flex-col gap-0.5">
                        <div
                            class={"flex items-center justify-between text-xs sm:text-sm italic " +
                                styles.fadedColor}
                        >
                            <h4>Progress</h4>
                            <h4>{count} / 20</h4>
                        </div>
                        <div class={" relative h-2 " + styles.progressBarColor}>
                            <div
                                class="h-full absolute top-0 left-0 bg-blue-400"
                                style={`width: ${(count * 100) / 20}%;`}
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div> -->
        <a
            href="/blog"
            class={"  rounded border px-2 py-1 duration-200  hover:opacity-60 sm:mr-2 text-sm sm:text-base poppins flex items-center gap-2 "}
        >
            <!-- <i class="fa-solid fa-scroll hidden sm:inline"></i> -->
            <h4>Blog</h4>
        </a>
        <!-- <a
            href="/blog"
            class={"  border duration-200 border-solid hover:opacity-60 rounded px-3 sm:px-4 py-1.5 md:px-5 text-sm sm:text-base poppins flex items-center gap-2 "}
        >
            <i class="fa-solid fa-scroll hidden sm:inline"></i>
            <h4>Blog</h4>
        </a> -->
    </div>
</header>
