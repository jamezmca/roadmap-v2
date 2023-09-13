<script>
    import BackHome from "../../../components/BackHome.svelte";
</script>

<main
    class="flex-1 p-4 max-w-prose mx-auto w-full flex flex-col gap-8 sm:gap-10 md:gap-14 min-h-[400px] sm:min-h-[500px] sm:pt-6 md:pt-10 jobApplications"
>
    <h1 class="text-2xl sm:text-3xl md:text-5xl duration-200">
        How I learned to Code in 6 Months & Got a Job Offer (self-taught)
    </h1>
    <p>
        I quit my job in April 2021, self-taught programming/web development &
        landed a Remote Full Stack job in November 2021 (based in Vancouver,
        Canada); all without spending a dime. Figured someone might find a
        factual time-history of my experience useful -_- Net amount of LeetCode
        time was 0 hours.
    </p>
    <div class="flex flex-col gap-1">
        <img
            src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*eA39Oxpm1IQKFgK0VIRfKw.png"
            alt="job offer"
        />
        <p class="opacity-70 text-center text-xs sm:text-sm">
            My Acceptance Email
        </p>
    </div>
    <section class="flex flex-col gap-4">
        <h3 class="font-semibold text-xl sm:text-2xl">Table of Contents</h3>
        <ul class="flex flex-col gap-4">
            <li
                class="list-inside list-disc italic cursor-pointer hover:underline"
            >
                <a href="#learning"
                    ><p>Learning Progression / Tech Timeline / Resources</p>
                </a>
            </li>
            <li
                class="list-inside list-disc italic cursor-pointer hover:underline"
            >
                <a href="#challenges">
                    <p>Greatest Challenges & How I Overcame Them</p>
                </a>
            </li>
            <li
                class="list-inside list-disc italic cursor-pointer hover:underline"
            >
                <a href="#takeaways">
                    <p>
                        Major Takeaways / Key Learnings (If I were to start
                        over)
                    </p>
                </a>
            </li>
        </ul>
    </section>
    <section class="flex flex-col gap-4">
        <h3 class="font-semibold text-xl sm:text-2xl">Disclaimer</h3>
        <p>
            The timeline is an un-opinionated, fact for fact rundown of my
            experience; the remainder is obviously just my opinion based on my
            experiences.
        </p>
    </section>
    <section class="flex flex-col gap-4" id="learning">
        <h3 class="font-semibold text-xl sm:text-2xl">
            Learning Progression / Tech Timeline / Resources
        </h3>
        <p>
            For this section, i’ll walk through my experience and then for each
            step, summarize it, and add my personal timeline for that learning
            progression. I had no notable prior experience with programming, so
            we’re starting fresh.
        </p>
        <p>
            <b>To begin</b>, I had a conversation with three of my friends who
            were Software Engineers, asking for any resources they had to learn
            programming. One friend recommended I learn JavaScript from
            <a
                class="underline"
                href="https://www.freecodecamp.org/learn"
                target="_blank">FreeCodeCamp.org</a
            >, completing their JavaScript Algorithms and Data Structures
            course.
        </p>
        <h4 class="p-4 italic">
            1. Learn JavaScript — FreeCodeCamp’s JavaScript Algorithms and Data
            Structures course (2–4 weeks, 3–4 hours per day).
        </h4>
        <p>
            This course was highly interactive and stepped through the learning
            hurdles in JavaScript really smoothly. They provide an excellent
            description of a topic, and then give you a challenge to complete
            for each concept inside of their own Integrated Development
            Environment (IDE). The challenges were all at an appropriate
            difficulty level and if I was unable to solve a challenge, then
            their answers were very explicit and easy to understand. This
            certificate says that it takes 300 hours but I found this to be a
            fairly conservative estimate.
        </p>
        <p>
            <b>Step 2</b>, was to complete their
            <b>Responsive Web Design</b> certificate. At this point, I had come to
            note that HTML CSS & JavaScript was the essential trio to get liftoff
            and so this HTML & CSS certificate was the natural progression.
        </p>
        <h4 class="p-4 italic">
            2. Learn HTML & CSS — FreeCodeCamp’s Responsive Web Design
            Certificate (2–4 weeks, 3–4 hours per day).
        </h4>
        <p>
            <b>Step 3</b>; Upon completing the Responsive Web Design
            certificate, I started applying for jobs; not sure where that
            audacity came from but I quickly learned that this level of
            accreditation was insufficient. Every job posting wanted me to link
            my portfolio website, which I didn’t have, and honestly I still
            didn’t know how to develop or deploy a website at this point (I had
            just been using FreeCodeCamp’s IDE).
        </p>
        <p>
            So I completed <a
                class="underline"
                href="https://www.youtube.com/watch?v=_xkSvufmjEs"
                target="_blank">Kevin Powell’s Web Portfolio YouTube tutorial</a
            > (2hrs). I also downloaded Visual Studio to code it in. This tutorial
            finished off with purchasing a domain and hosting the project so it was
            live; a great experience.
        </p>
        <h4 class="p-4 italic">
            3. Finishing this portfolio project; launching my first HTML & CSS
            static website (10–15hrs).
        </h4>
        <p>
            And now I had a portfolio, but I had no projects inside said
            portfolio so this nicely introduces step 4.
        </p>
        <p>
            <b>Step 4</b>; For step 4, I was looking at job postings for the
            jobs I wanted to see what skills I didn’t have. This information was
            going to guide the direction of my projects, and projects are
            critical because they are the only real credibility you have to your
            name. Nearly every posting was requesting React, and so I learned
            React Native from
            <a
                class="underline"
                href="https://www.youtube.com/watch?v=qSRrxpdMpVc&t=10372s"
                target="_blank">Academinds React-Native YouTube tutorial</a
            > (5hrs).
        </p>
        <h4 class="p-4 italic">
            4.1. Finish Academind’s React-Native Youtube tutorial (20hrs).
        </h4>
        <p>
            Following this tutorial, I had all the essential skills to develop
            my own basic CRUD mobile app; a Todo app. I stylized it myself so it
            looked atrocious, but I did ultimately deploy it to the app store,
            and added it to my portfolio.
        </p>
        <h4 class="p-4 italic">
            4.2. Code my own React-Native app with basic CRUD functionality
            [read/write to device localstorage] | (1–2 weeks).
        </h4>
        <p>
            <b>Step 5</b>; Waste a whole lot of time on random little youtube
            tutorials that I didn’t understand
            <i>[this step is not mandatory to follow but I was directionless]</i
            > (1 month).
        </p>
        <p>
            <b>Step 6</b>; After a period of aimless meandering, I finally found
            some direction and inspiration for my second project. I would
            occasionally put out job applications, get no response, and so I
            knew I needed something more. I settled on building an E-commerce
            store with <b>Stripe & React</b>, following another youtube tutorial
            at approximately 5hrs in length (can’t find the link for my life
            :’[). After completing the tutorial, I rebranded the site, added my
            own products, and proceeded to make zero sales; nice. Still, another
            project to the portfolio, all hosted live and everything.
        </p>
        <h4 class="p-4 italic">
            6. Code a functional E-commerce store in React + Stripe +
            Commerce.js (1–2 weeks).
        </h4>
        <p>
            <b>Step 7</b>; Still no job response — lame. Time to start
            diversifying my applications away from Frontend alone, branching
            outwards to include Backend and Full Stack. This was achieved by
            learning Node.js + Express.js + MongoDB. This took me a while and in
            retrospect, I would breakdown this step into two parts if I was
            doing it again. Part 1 would be learning a bit about networking and
            HTTP requests etc, and then part 2 would be learning Node.js +
            Express.js, and running a server.
        </p>
        <h4 class="p-4 italic">
            7. Learn a bit about Node.js, Express.js & servers (1- weeks).
        </h4>
        <p>
            Nothing really came out of this stage except I had a bunch of random
            GitHub repos that didn’t really do me much good.
        </p>
        <p>
            <b>Step 8</b>; Step 8 was my first <b>Full Stack</b> project, and also
            my lucky number 3 project. This one took me ages and it used React +
            Firebase Auth + Firestore DB tech stack. Deployed on Netlify. Firebase
            is a Paas service which basically means that handle all the backend stuff
            for you and make it super easy for you to develop full stack applications
            without the hassle of deploying a Node.js + MongoDB backend with JWT
            auth and then having everyone hack it to pieces as soon as it’s live.
            Super convenient and I found it was a great compromise for getting a
            handle on Full Stack Development.
        </p>
        <h4 class="p-4 italic">
            8. First Full Stack CRUD project with React + Firebase [auth + db]
            (1 month).
        </h4>
        <p>
            To get started on Full Stack development with Firebase, I watched a
            tutorial that demonstrated how to implement Firebase Auth in a React
            project, and covered things like protected routes. From there it was
            super easy to bring in the Firestore database just by reading their
            documentation and having all the CRUD functionality hid behind a
            authentication wall, where each CRUD function was associated with a
            user ID that is created when you use Firebase Auth.
        </p>
        <p>
            <b>Step 9</b>; Applying for 3–4 jobs per day. I had three projects
            and I felt I had a good array of technology demonstrated across the
            projects in my portfolio. Adding in some Full Stack/DB+Auth stuff
            really helped boost my response numbers. I also learned Python
            because it seemed like every job was looking for Python. This took
            me half of a 5hr Data Science YouTube tutorial. Super easy to
            translate from JavaScript to Python in my experience.
        </p>
        <h4 class="p-4 italic">
            9. Apply for jobs (1–2months) + learn Python (3–5hrs).
        </h4>
        <p>
            <strong
                >Total experience around 6 months, averaging 4–5hrs per day, 5–6
                days per week.</strong
            >
        </p>
    </section>
    <section class="flex flex-col gap-4" id="challenges">
        <h3 class="font-semibold text-xl sm:text-2xl">
            Greatest Challenges & How I Overcame Them
        </h3>
        <p>
            The two challenges I found that we’re a real pain were: <i
                >Imposter Syndrome and Tutorial Hell</i
            >.
        </p>
        <p>
            <strong>Imposter Syndrome</strong> was a real pain because I had no support
            or network for reassurance. And every job I applied for had around 200
            applicants; what a pain, really demotivating and demoralizing.
        </p>
        <p>
            For me the solution was to realize two key things. The first was
            that it’s not really a continuous spectrum of developers. It’s a
            pragmatic world, we’re not all ranked; more analogous to a discrete
            system of <b class="italic">can code a Full Stack app</b> and
            <b class="italic">can't code a Full Stack app</b>. You either can or
            you can’t; it doesn’t matter if people are way better than you, as
            long as you can both code a Full Stack app.
        </p>
        <p>
            The second thing to realize was that I needed to shift my focus;
            less on how good people were at developing, and more on how good I
            was as a learner. People can be better developers than me but what
            matters more for junior SWE roles is that you’re a good learner. You
            know how to research, you can give it a shot, and you are receptive
            to feedback. Helped me not care about how good everyone else was
            with their snarky SWE qualifications.
        </p>
        <p>
            <strong>Tutorial Hell</strong> was also a mofo but the solution is actually
            chill. I found that I just had to start off making super minor changes
            to tutorials I followed. Starts off just being a font-size, text color
            or background picture, and then it just snowballs out of control until
            you have a new application. Adapting some of the logic stuff is good
            too, you really understand how it all works which means it’s way easier
            to reproduce.
        </p>
    </section>
    <section class="flex flex-col gap-4" id="takeaways">
        <h3 class="font-semibold text-xl sm:text-2xl">
            Greatest Challenges & How I Overcame Them
        </h3>
        <h4 class="p-4 italic font-semibold text-lg sm:text-xl">
            Fastest Way to Learn Coding (in my experience)
        </h4>
        <p>
            This tip is outside of learning basic HTML CSS & JavaScript and is
            more about general programming thereafter — fastest way to learn
            HTML CSS & JavaScript is defo FreeCodeCamp imo. For everything else,
            the system I use is as follows:
        </p>
        <ul class="flex flex-col gap-2">
            <li class="list-decimal list-inside">
                Find a good tutorial or article that describes a new concept.
            </li>
            <li class="list-decimal list-inside">
                Code out said tutorial for myself.
            </li>
            <li class="list-decimal list-inside">
                *Critical* Leave loads of comments with explanations on
                functionalities all throughout my code (guarantees you
                understand everything and further solidifies memories).
            </li>
            <li class="list-decimal list-inside">Save code to GitHub.</li>
            <li class="list-decimal list-inside">
                Adapt the project; keep the same code skeleton, but repurpose
                the project into my own project (this might be a new color
                scheme, layout, functionality). An example would be to follow a
                tutorial for a CRUD app with Auth + DB. I would keep Auth + DB
                system, rework the layout and app function and update the CRUD
                system accordingly.
            </li>
            <li class="list-decimal list-inside">
                Save new project to GitHub.
            </li>
            <li class="list-decimal list-inside">
                Whenever I start a new project that I know will use a similar
                infrastructure, first 2–3 projects like this I’ll just revisit
                GitHub repo with all my amazing comments I left myself. After
                that, I can generally remember if it’s something I do often
                (which is convenient as I naturally end up remembering only the
                stuff that is relevant to me).
            </li>
        </ul>
        <h4 class="p-4 italic font-semibold text-xl sm:text-2xl">Resume</h4>

        <a
            href="https://www.reddit.com/r/jobs/comments/7y8k6p/im_an_exrecruiter_for_some_of_the_top_companies/"
            target="_blank"
            class="w-full truncate"
            >https://www.reddit.com/r/jobs/comments/7y8k6p/im_an_exrecruiter_for_some_of_the_top_companies/</a
        >
        <h4 class="p-4 italic font-semibold text-xl sm:text-2xl">
            Cover Letter
        </h4>
        <a
            href="https://www.reddit.com/r/jobs/comments/37rgr1/heres_the_best_cover_letter_ive_ever_seen/"
            target="_blank"
            class="w-full truncate"
            >https://www.reddit.com/r/jobs/comments/37rgr1/heres_the_best_cover_letter_ive_ever_seen/</a
        >
        <h4 class="p-4 italic font-semibold text-xl sm:text-2xl">GitHub</h4>
        <p>
            Best to get one ASAP. Employers and hiring people apparently go
            mental over the activity log. The sooner you can start committing
            code to your GitHub and getting your activity up the better, cause
            it is the #1 way to show the duration and intensity of your
            experience. You get one 3 months late, and you miss out on bragging
            about 3 months of dev time. I’d recommend commit a minimum of 1
            thing per day so the whole thing is green patches (even if it’s just
            adding a meaningless comment to a repo and pushing that commit).
        </p>
        <h4 class="p-4 italic font-semibold text-xl sm:text-2xl">
            Applying for Jobs/Networking
        </h4>
        <p>
            Basically just need a simple & clean portfolio with some contact
            details, about you section, and 3 projects imo. Each project should
            have a link to the live page, and the GitHub repo. GitHub repos
            should be tidy, and ideally each project would have a nice Readme.md
            file that details the project. The 3 projects should be pinned to
            top of your GitHub. LinkedIn page should also be clean but also
            doesn’t need to be OTT. Just shows your previous experience and how
            it relates to the job you want (generally most roles demonstrate
            problem solving, communication and leadership).
        </p>
        <p>
            *Critical* For each job you put out, find either someone senior in
            the tech department of that company, or the hiring manager/person
            themselves. Connect with them on LinkedIn and append the following
            note:
        </p>
        <p class="italic opacity-80 p-2">
            Hi [name],<br />
            I hope this message finds you well.<br />
            I just noticed your job posting for a [insert_job_posting_title] and
            as a seasoned [insert_your_relevant_role_experience], I feel I would
            be a great fit for the role.<br />
            I’d love to connect and chat about the opportunity.<br />
            Cheers, [your_name]
        </p>
        <p>
            Literally gets you free interviews (also got me an earlier offer —
            didn’t go forwards with it though).
        </p>
        <h4 class="p-4 italic font-semibold text-xl sm:text-2xl">
            Communication/Soft Skills
        </h4>
        <p>
            This ultimately landed me my job. I was initially rejected cause the
            role was full (I applied late), and a week later the hiring dude
            came back to me and said he liked my communication skills and said
            they wanted to make something work.
        </p>
        <p>
            What good communication meant for me was, for every meeting, send a
            follow up email saying ‘Thanks for your time’, ‘Very grateful for
            the opportunity to meet you and your team, and hear about what
            you’re doing’, ‘Take care’; all these kind of things. Even when I
            was rejected, I followed up saying ‘thanks a lot, I learned heaps
            and am very appreciative for the experience and your time’ or
            something along those lines. I actually think it was my response to
            rejection that was the key one, but just generally if you can
            demonstrate gratitude and the desire to learn and improve you’ll be
            right.
        </p>
        <p>Ayo let’s go that’s it thanks for reading.</p>
    </section>
    <section class="flex flex-col gap-4" id="takeaways">
        <h3 class="font-semibold text-xl sm:text-2xl">
            Video version of this article
        </h3>
        <div class=" flex flex-col aspect-video relative">
            <iframe
                class="w-full h-full"
                src="https://www.youtube.com/embed/nP0-oYGiqts"
                title="How I learned to Code in 6 MONTHS &amp; Got a Job Offer (Self-Taught)"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                allowfullscreen
            />
        </div>
    </section>
    <BackHome />
</main>

<svelte:head>
    <title>Webdev Roadmap · Blog · Learn to code</title>
</svelte:head>
