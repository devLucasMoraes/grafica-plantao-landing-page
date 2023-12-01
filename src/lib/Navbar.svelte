<script>
  import { page } from "$app/stores";
  import Logo from "./Logo.svelte";

  const itens = [
    { href: "/", label: "Início" },
    { href: "/sobre", label: "Sobre nós" },
    { href: "/produtos", label: "Produtos" },
    { href: "/contato", label: "Contato" },
  ];
</script>

<a href="/">
  <Logo />
</a>

{#each itens as { href, label }}
  {#if $page.url.pathname === href}
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
