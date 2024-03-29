<script>
    import { location } from "$lib/location"
    const links = [
        { text: "ホーム", href: "/" },
        { text: "参加方法", href: "/how-to-join" },
        { text: "ルール", href: "/rules" },
        { text: "概要", href: "/overview" },
        { text: "採用情報", href: "/recruit" },
        { text: "リンク", href: "/links" },
        { text: "寄付", href: "/donation" },
        { text: "お問い合わせ", href: "/contact" }
    ];
</script>

<div class="flex items-center gap-[25px] font-jp text-[14px] font-[600] text-white fixed right-0 p-7 pr-9 z-50">
    {#each links as link}
        <a href={link.href} class:active={$location === link.href}>{link.text}</a>
    {/each}
</div>

<style>
    a {
        position: relative;
    }
    a:before {
        position: absolute;
        content: "";
        right: 0;
        bottom: -2px;
        height: 1px;
        width: 0;
        background: white;
        transition: all 0.3s;
    }
    a:hover:before,
    .active:before {
        left: 0;
        width: 100%;
    }
</style>