<script>
    import Header from "$lib/components/Header.svelte"
    import Bg from '$lib/assets/rules.png'
    import Uneko from '$lib/assets/nekozouneko.png'
    import Move from '$lib/assets/move1.png'
    import { goto } from "$app/navigation"
    import Delay from "$lib/components/Delay.svelte";
    import Icon from "@iconify/svelte";
    import Button from "$lib/Button.svelte";
    import Bar from "$lib/Bar.svelte";
</script>

<div class="flex items-center justify-center">
    <div class="w-[50%]">
        <div class="w-[30rem] m-auto">
            <img class="w-[10rem]" src={Uneko} alt="">
            <Delay delay={200}>
                <div class="flex items-center gap-3 font-body font-[600] m-auto mt-[2rem]">
                    <p class="min-w-max">Rules and terms of use/service</p>
                    <Bar/>
                </div>
            </Delay>
            <div class="font-jp text-[40px] font-[900] m-auto w-[30rem] leading-[3.3rem] mt-[5px]">
                <Delay delay={250}><p class="font-body ml-[3px]">ルール・規約</p></Delay>
            </div>
            <Delay delay={300}>
                <div class="mt-5 font-jp">
                    <p>ルールと利用規約はこちらのブログで掲載しております！</p>
                    <a href="https://srv.nekozouneko.net/archives/31" class="flex items-center gap-1 text-[20px] font-[400] text-blue-400 bg-blue-400 bg-opacity-20 hover:bg-opacity-30 transition-all w-max rounded-full px-4 py-1 mt-2">
                        <Icon icon="material-symbols:link"/>
                        <p class="text-[18px] mb-[2px]">こちらのリンクから</p>
                    </a>
                </div>
            </Delay>
            <Delay delay={350}>
                <Button href="/overview" icon="ph:arrow-down">概要</Button>
            </Delay>
        </div>
    </div>
    <img class="h-screen w-[50%] bg-cover bg-no-repeat" src={Bg} alt="Nekozouneko Server">
</div>