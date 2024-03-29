<script lang="ts">
    import Header from "$lib/components/Header.svelte"
    import Bg from '$lib/assets/home.png'
    import Uneko from '$lib/assets/nekozouneko.png'
    import Move from '$lib/assets/move1.png'
    import { goto } from "$app/navigation"
    import { fade } from "svelte/transition"
    import type { CarouselAPI } from "$lib/components/ui/carousel/context"
    import Delay from "$lib/components/Delay.svelte"
    import Icon from "@iconify/svelte"

    import * as Card from "$lib/components/ui/card"
    import * as Carousel from "$lib/components/ui/carousel"
    import Button from "$lib/Button.svelte";
    import Bar from "$lib/Bar.svelte";

    let api: CarouselAPI
    let current = 0

    let primary = '#2a2a2a'

    $: if (api) {
        current = api.selectedScrollSnap()
        api.on("select", () => {
            current = api.selectedScrollSnap()
            if(current === 4) {
                primary = '#CDB19C'
            } else {
                primary = '#2a2a2a'
            }
        })
    }

    const cards = [
        {name: "サバイバル", title: "シンプル、自由、仲間", description: "複雑なプラグインやMODの知識はいらない！シンプルに周りの仲間とサバイバルをしよう。<br/><br/>サバイバルサーバーでは、難しい追加要素はほとんどありません。<br/>入ってすぐに他のプレイヤーと馴染めるように、初期アイテムが用意されています！<br/><br/>また、最初のスポーンでは発展して新しい建築が困難になってしまってランダムで空いている場所に飛び込んで遊ぶことができます！"},
        {name: "国家", title: "地震の国で経済トップへ", description: "日々遊ぶ仲間と国や町を作ろう、<br/>きっと皆集まれば大きな経済力になるだろう。<br/><br/>国家サーバーでは、国や町の作成ができるTownyというプラグインが導入されています。<br/>また、経済要素の強みによりそれぞれの町の経済力で互いに競い合うことができます。<br/><br/>オリジナルな情勢を持ち、個性ある町をあなたも作ってみましょう。"},
        {name: "超", title: "超えられぬ便利さ、偉大", description: "普通のサバイバルに飽きてしまった、<br/>普通のサバイバルが私には難しい、<br/><br/>超サーバーでは、様々な便利要素を追加するプラグインが多数導入されています。一風サバイバルとは少し変わった楽しさがあります！<br/><br/>また、多少プラグインに疎い方でも楽しんでご利用いただけるようにコマンド・荒らし行為等によるサポートに運営一同力を日々費やしております。"},
        {name: "採掘", title: "作業好きにはたまらない", description: "普段行う整地、なんだかずっとやれてしまう、<br/>その作業心に手を差し伸べたサーバー。<br/><br/>採掘サーバー（The Mining）では、整地による採掘だけにフォーカスしました。作業が好きな方や掘る楽しさに気づける楽しいサーバーです。<br/><br/>自分だけのピッケルを作り、時にはそれに価値を付け、スローライフな面を兼ね備えています。ぜひ一度足を踏み入れてみてください。"},
        {name: "KissaMC", title: "争うはすぐそこに、争え", description: "戦う日が今日やってきました、<br/>自身のPvPテクニックと誠意でトップを目指そう。<br/><br/>KissaMCはNekozouneko Server管轄下の独立ミニゲームサーバーです。様々なPvPゲームを取り揃えており、<br/><br/>自分だけのピッケルを作り、時にはそれに価値を付け、スローライフな面を兼ね備えています。<br/>ぜひ一度足を踏み入れてみてください。"}
    ]
</script>

<div class="flex items-center justify-center transition-all text-white" style="background: {current === 4 ? 'rgba(151,91,48,0.5)' : '#262626'}">
    <div class="w-[50%]">
        <div class="w-[30rem] m-auto">
            <img class="w-[10rem]" src={Uneko} alt="">
            <Delay delay={200}>
                <div class="flex items-center gap-3 font-body font-[600] m-auto mt-[2rem]">
                    <p class="min-w-max">Server Overview</p>
                    <Bar dark/>
                </div>
            </Delay>
            <div class="font-jp text-[40px] font-[900] m-auto w-[30rem] leading-[3.3rem] mt-[5px]">
                <Delay delay={250}><p>サーバー概要</p></Delay>
            </div>

            <Delay delay={300}>
                <div class="relative">
                    {#key current}
                        <div>
                            <p class="vertical absolute left-0 top-0 font-jp font-[500] mt-1" transition:fade>{cards[current].name}</p>
                        </div>
                    {/key}
                    <Carousel.Root class="w-full max-w-[24rem] ml-12 mt-5" bind:api>
                        <Carousel.Content>
                            {#each cards as card}
                                <Carousel.Item>
                                    <div class="p-1">
                                        <Card.Root class="border-transparent font-jp text-white" style="background: {primary}">
                                            <Card.Content class="h-[20rem]">
                                                <p class="mt-5 mb-3.5 font-[600] text-[26px]">{card.title}</p>
                                                <p class="mt-2 text-[14px]">{@html card.description}</p>
                                            </Card.Content>
                                        </Card.Root>
                                    </div>
                                </Carousel.Item>
                            {/each}
                        </Carousel.Content>
                        <Carousel.Previous class="w-[2.5rem] h-[2.5rem] border-none" style="background: {primary}" />
                        <Carousel.Next class="w-[2.5rem] h-[2.5rem] border-none" style="background: {primary}" />
                    </Carousel.Root>
                </div>
            </Delay>

            <Delay delay={350}>
                <Button href="/recruit" icon="ph:arrow-down" dark>採用情報</Button>
            </Delay>
        </div>
    </div>
    <img class="h-screen w-[50%] bg-cover bg-no-repeat" src={Bg} alt="Nekozouneko Server">
</div>

<style>
    .vertical {
        writing-mode: vertical-lr;
    }
</style>