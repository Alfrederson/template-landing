<script>
    export let backgroundImage = "";

</script>

<div class="hero min-h-screen" style="{backgroundImage && `background-image: url(${backgroundImage});`}">
    <div class="hero-overlay bg-opacity-60" />

    <slot/>
</div>
