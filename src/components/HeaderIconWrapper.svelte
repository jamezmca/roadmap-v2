<script>
    export let title;
</script>

<div class="grid place-items-center relative group">
    <slot />
    <div
        class="absolute opacity-0 pointer-events-none group-hover:opacity-60 duration-200 top-full mt-1.5 left-1/2 -translate-x-1/2 rounded-md   text-sm hidden sm:grid place-items-center"
    >
       <p class="whitespace-nowrap">{title}</p> 
    </div>
</div>
