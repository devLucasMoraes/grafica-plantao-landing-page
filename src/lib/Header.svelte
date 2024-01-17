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
      const currentScrollY = window.pageYOffset;

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
    class="container flex items-center justify-center p-6 mx-auto text-gray-200"
  >
    <Navbar />
  </div>
</nav>
