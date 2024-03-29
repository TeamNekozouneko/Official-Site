<script>
    import Header from "$lib/components/Header.svelte"
    import Bg from '$lib/assets/matuken.png'
    import Uneko from '$lib/assets/nekozouneko.png'
    import Move from '$lib/assets/move1.png'
    import { goto } from "$app/navigation"
    import Delay from "$lib/components/Delay.svelte";
    import Icon from "@iconify/svelte";
    import Button from "$lib/Button.svelte";
    import Bar from "$lib/Bar.svelte";
</script>

<div class="flex items-center justify-center bg-[#262626] text-white">
    <div class="w-[50%]">
        <div class="w-[30rem] m-auto">
            <img class="w-[10rem]" src={Uneko} alt="">
            <Delay delay={200}>
                <div class="flex items-center gap-3 font-body font-[600] m-auto mt-[2rem]">
                    <p class="min-w-max">How to Join</p>
                    <Bar dark/>
                </div>
            </Delay>
            <div class="font-jp text-[40px] font-[900] m-auto w-[30rem] leading-[3.3rem] mt-[5px]">
                <Delay delay={250}><p>参加方法</p></Delay>
            </div>
            <Delay delay={350}>
                <Button href="/rules" dark>ルール</Button>
            </Delay>
        </div>
    </div>
    <img class="h-screen w-[50%] bg-cover bg-no-repeat" src={Bg} alt="Nekozouneko Server">
</div>