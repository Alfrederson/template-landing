<script>

    import "aos/dist/aos.css"
    import AOS from 'aos'

    import { onMount } from "svelte";

    import { companyName, companyEst } from "./data";


    import "../app.css";
    import Footer from "../lib/components/Footer.svelte";
    import Header from "../lib/components/Header.svelte";  

    onMount(()=>{
        AOS.init()
    })

</script>

<svelte:head>
    <title>{companyName}</title>
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-9754268803581055"
    crossorigin="anonymous"></script>
</svelte:head>

<Header {companyName}/>
<div style="overflow-x:hidden;">
    <slot />
</div>
<Footer {companyName} {companyEst} />
