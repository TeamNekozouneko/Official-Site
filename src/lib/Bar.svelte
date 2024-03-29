<script>
    import { onMount } from "svelte"

    export let dark = false

    let width = 0
    onMount(() => {
        setTimeout(() => {
            width = 100
        }, 300)
    })
</script>

<div class="h-[2px] bg-gradient-to-r from-{dark ? 'neutral-300' : 'black'} to-transparent transition-all duration-[1s]" style="width: {width}%"/>