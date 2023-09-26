<script>
    import BackHome from "../../components/BackHome.svelte";
    import store from "../../store";

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

    let blogs = [
        {
            name: "Everything you need to know to Land Your Developer Job! (A comprehensive guide).",
            description:
                "Want to land you very own developer job? Guarantee your success by following this comprehensive step-by-step guide that teaches everything you need to know about preparing your professional image, mastering the art of networking, winning in interviews, and getting your job offer.",
            href: "/blog/job_applications",
        },
        {
            name: "How I learned to Code in 6 Months & Got a Full Stack Developer Job Offer (self-taught).",
            description:
                "It took a lot of courage to quit my job and pursue a career as a developer, but I knew it was what I wanted and was willing to put in the hard work to make it happen. So this is the story of how I learned to code (self-taught) and ultimately landed my dream remote developer job!",
            href: "/blog/learn_to_code",
        },
    ];
</script>

<section
    class="flex flex-col gap-10 p-4 pt-8 sm:pt-10 md:pt-14 sm:gap-14 md:gap-20"
>
    <h1 class="text-3xl sm:text-4xl md:text-5xl font-semibold text-center">
        Blog
        <span class={" " + styles.accentColor}>Articles</span>
    </h1>
    <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
        {#each blogs as blog, index}
            <a
                href={blog.href}
                class="flex gap-4 sm:gap-6 md:gap-8 group cursor-pointer"
            >
                <p
                    class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold"
                >
                    0{index + 1}
                </p>
                <div class="flex flex-col gap-4 sm:gap-6 md:gap-8">
                    <h3
                        class="text-2xl sm:text-3xl md:text-4xl group-hover:text-blue-400 duration-200"
                    >
                        {blog.name}
                    </h3>
                    <p class="font-light">{blog.description}</p>
                </div>
            </a>
        {/each}
    </div>
    <BackHome />
</section>

<svelte:head>
    <title>Web Developer Roadmap · Blog</title>
    <meta
        name="description"
        content="Everything you need to know about the Web Development Roadmap and landing a developer job."
    />
</svelte:head>
