<script>
  import { page } from "$app/stores";
  import { onMount } from "svelte";
  import Logo from "./Logo.svelte";

  let isOpen = false;

  onMount(() => {
    window.addEventListener("scroll", () => {
      if (isOpen) {
        isOpen = false;
      }
    });
  });

  function toggleMenu() {
    isOpen = !isOpen;
  }

  const itens = [
    { href: "/", label: "Início" },
    { href: "#about", label: "Sobre nós" },
    { href: "#products", label: "Produtos" },
    { href: "#contact", label: "Contato" },
  ];
</script>

<div class="flex items-center justify-between">
  <a href="/">
    <Logo />
  </a>

  <!-- Mobile menu button -->
  <div class="flex md:hidden">
    <button
      on:click={toggleMenu}
      class="text-gray-500 dark:text-gray-200 hover:text-gray-600 dark:hover:text-gray-400 focus:outline-none focus:text-gray-600 dark:focus:text-gray-400"
      aria-label="Toggle menu"
    >
      {#if isOpen}
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="w-6 h-6"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      {:else}
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="w-6 h-6"
          viewBox="0 0 24 24"
          stroke-width="2"
          stroke="currentColor"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M4 8h16M4 16h16"
          />
        </svg>
      {/if}
    </button>
  </div>
</div>

<!-- Mobile Menu open/closed based on isOpen variable -->
<div
  class="absolute inset-x-0 z-20 w-full px-6 py-4 transition-all duration-300 ease-in-out bg-sky-500 md:mt-0 md:p-0 md:top-0 md:relative md:bg-transparent md:w-auto md:opacity-100 md:translate-x-0 md:flex md:items-center"
  class:hidden={!isOpen}
  class:flex={isOpen}
>
  <div class="flex flex-col md:flex-row md:mx-6">
    {#each itens as { href, label }}
      {#if $page.url.href === href}
        <a
          {href}
          class="text-gray-800 transition-colors duration-300 transform dark:text-gray-200 border-b-2 border-sky-800 mx-1.5 sm:mx-6"
          >{label}</a
        >
      {:else}
        <a
          {href}
          class="border-b-2 border-transparent hover:text-gray-800 transition-colors duration-300 transform dark:hover:text-gray-200 hover:border-sky-800 mx-1.5 sm:mx-6"
          >{label}</a
        >
      {/if}
    {/each}
  </div>
</div>
