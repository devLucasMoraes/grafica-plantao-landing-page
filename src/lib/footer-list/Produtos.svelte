<script>
  const produtos = [
    { href: "#", label: "Panfletos" },
    { href: "#", label: "Folders" },
    { href: "#", label: "Cartazes" },
    { href: "#", label: "Livros" },
    { href: "#", label: "Revistas" },
    { href: "#", label: "Catálogos" },
    { href: "#", label: "Embalagens" },
    { href: "#", label: "Encartes" },
    { href: "#", label: "Jornais" },
    { href: "#", label: "Rótulos" },
  ];
</script>

<div>
  <h3 class="text-gray-700 uppercase dark:text-white">Produtos</h3>
  {#each produtos as { href, label }}
    <a
      {href}
      class="block mt-2 text-sm text-gray-600 dark:text-gray-400 hover:underline"
      >{label}</a
    >
  {/each}
</div>
