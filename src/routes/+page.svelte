<script>
    import Footer from "../lib/components/Footer.svelte";
    import Header from "../lib/components/Header.svelte";
    import Hero from "../lib/components/Hero.svelte";
    import HeroOverlay from "../lib/components/HeroOverlay.svelte";

    const
        currentDate = new Date().getFullYear()

    const
        companyName = "R718 Co.",
        companyEst  = `© R718 1988 - ${currentDate}`

</script>

<Header
    {companyName}
/>
<HeroOverlay/>
<Footer
    {companyName}
    {companyEst}
/>