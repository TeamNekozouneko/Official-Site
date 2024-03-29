<script>
    import Icon from "@iconify/svelte"

    export let href = '/'
    export let icon = ''
    export let dark = false
</script>

<a href={href} class="flex items-center mt-[8rem] w-max rounded-full px-5 py-3 transition {dark ? 'hover:bg-neutral-900' : 'hover:bg-neutral-100'} cursor-pointer font-jp font-[500] gap-1">
    <Icon icon={icon}/>
    <p><slot/></p>
</a>