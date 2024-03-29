<script>
    import { fly, fade } from 'svelte/transition'
    export let pathname = ''
    export let className = ''
</script>


{#key pathname}
    <div in:fly={{ y: 5, duration: 400, delay: 400 }} out:fly={{ y: 5, duration: 400 }} class="hidden-scrollbar {className}">
        <slot />
    </div>
{/key}