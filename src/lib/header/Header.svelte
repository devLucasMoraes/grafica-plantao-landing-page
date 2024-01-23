<script>
  import { onMount } from "svelte";
  import Navbar from "./Navbar.svelte";

  /**
   * @type {HTMLElement}
   */
  let navbar;

  let lastScrollY = 0;

  onMount(() => {
    const handleScroll = () => {
      const currentScrollY = window.scrollY;

      if (currentScrollY < lastScrollY) {
        navbar.classList.remove("-translate-y-full");
      } else {
        navbar.classList.add("-translate-y-full");
      }

      lastScrollY = currentScrollY;
    };

    window.addEventListener("scroll", handleScroll);

    return () => {
      window.removeEventListener("scroll", handleScroll);
    };
  });
</script>

<nav
  class="shadow bg-sky-500 fixed top-0 left-0 z-10 w-full transition-all"
  bind:this={navbar}
>
  <div
    class="container px-6 py-4 mx-auto md:flex md:justify-between md:items-center text-gray-200"
  >
    <Navbar />
  </div>
</nav>
