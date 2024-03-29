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
                    <p class="min-w-max">For your donation</p>
                    <Bar/>
                </div>
            </Delay>
            <div class="font-jp text-[40px] font-[900] m-auto w-[30rem] leading-[3.3rem] mt-[5px]">
                <Delay delay={250}><p class="font-body ml-[3px]">寄付について</p></Delay>
            </div>

            <Delay delay={300}>
                <p class="font-jp mt-5 font-bold">本サーバーの維持費・運営費は日々ご利用いただいているユーザー様からのご寄付により支えられています。<br/>ご寄付いただいた方にはサーバー内で利用可能な特典を用意しておりますので、私たちNekozouneko Serverのためにご支援いただければ大変幸いです。</p>
            </Delay>
            <Delay delay={350}>
                <a href="/" class="flex items-center gap-1 font-jp font-[500] text-[20px] bg-red-500 text-red-400 bg-opacity-20 transition-all hover:bg-opacity-30 px-4 py-1 rounded-full w-max mt-3">
                    <Icon icon="bxs:donate-heart"/>
                    <p>寄付はこちらから</p>
                </a>
            </Delay>

            <Delay delay={400}>
                <Button href="/contact" icon="ph:arrow-down">お問い合わせ</Button>
            </Delay>
        </div>
    </div>
    <img class="h-screen w-[50%] bg-cover bg-no-repeat" src={Bg} alt="Nekozouneko Server">
</div>