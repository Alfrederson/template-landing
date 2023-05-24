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

<style>
    :global(body) {
        overflow-x: hidden;
        min-height: 100vh;;
    }
</style>

<svelte:head>
    <title>{companyName}</title>
</svelte:head>

<Header {companyName}/>
<slot />
<Footer {companyName} {companyEst} />
