<script lang="ts">
    import "../app.pcss"
    import '@fontsource-variable/inter'
    import '@fontsource-variable/noto-sans-jp'
    import Header from "$lib/components/Header.svelte"
    import { onMount } from "svelte"
    import { onNavigate } from "$app/navigation"
    import { location } from "$lib/location"
    import Transition from "$lib/components/Transition.svelte";

    export let data

    onMount(() => {
        location.set(window.location.pathname)
    })

    onNavigate((c) => {
        if(c.to != null) {
            location.set(`${c.to.route.id}`)
        }
    })
</script>

<div>
    <Header/>
    <Transition pathname={data.pathname}>
        <slot/>
    </Transition>
</div>