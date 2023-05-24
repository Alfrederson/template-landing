<script>
    import { companyName, companyEst } from "./data";


    import "../app.css";
    import Footer from "../lib/components/Footer.svelte";
    import Header from "../lib/components/Header.svelte";  


</script>

<style>
    :global(body) {
        overflow-x: hidden;
        min-height: 100vh;;
    }
</style>


<Header {companyName}/>
<slot />

<Footer {companyName} {companyEst} />
