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
</svelte:head>

<Header {companyName}/>
<div style="overflow-x:hidden;">
    <slot />
</div>
<Footer {companyName} {companyEst} />
