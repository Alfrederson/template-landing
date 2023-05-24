<script>
    import { onMount } from "svelte";
    import ArrowRight from "./ArrowRight.svelte";

    export let
        companyName = "{companyName}"

    let scrollY = 0
    /**
     * @type {number | undefined}
     */
    let scrollTimeout = undefined

    onMount(()=>{
        window.addEventListener("scroll", (event) => {
            if(scrollTimeout !== undefined){
                clearTimeout( scrollTimeout )
            }
            scrollTimeout = setTimeout( ()=>{
                scrollY = window.scrollY
            }, 5)
        })
    })
</script>

<div class="sticky top-0 transition-all delay-150 navbar {scrollY < 10 ? "bg-base-100" : "backdrop-filter backdrop-blur"} z-10">
    <div class="dropdown">
        <button class="btn btn-ghost md:hidden">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h8m-8 6h16" /></svg>
        </button>
        <ul tabindex="0" class="menu menu-compact dropdown-content mt-3 p-2 shadow bg-base-100 rounded-box w-52">
          <li><a>Item 1</a></li>
          <li tabindex="0">
            <a class="justify-between">
              Parent
              <ArrowRight/>
            </a>
            <ul class="menu menu-compact dropdown-content mt-3 p-2 shadow bg-base-100 rounded-box w-52">
              <li><a>Submenu 1</a></li>
              <li><a>Submenu 2</a></li>
            </ul>
          </li>
          <li><a>Item 3</a></li>
        </ul>
    </div>

    <div class="flex-1">
      <a class="btn btn-ghost normal-case text-xl" href="/">{companyName}</a>
    </div>
    <div class="flex-none">
        <div class="hidden md:flex">
            <ul class="menu menu-horizontal px-1">
                <li><a>Item 1</a></li>
                <li tabindex="0">
                <a>
                    Parent
                    <svg class="fill-current" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><path d="M7.41,8.58L12,13.17L16.59,8.58L18,10L12,16L6,10L7.41,8.58Z"/></svg>
                </a>
                <ul class="p-2 bg-base-100">
                    <li><a>Submenu 1</a></li>
                    <li><a>Submenu 2</a></li>
                </ul>
                </li>
                <li><a>Item 3</a></li>
            </ul>
        </div>

    </div>
  </div>