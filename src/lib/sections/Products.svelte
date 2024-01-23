<script>
  let selectedCategory = "todos";

  const categories = [
    { name: "Todos", slug: "todos" },
    { name: "Cartazes / Panfletos / Encartes", slug: "panfletos" },
    { name: "Rótulos", slug: "rotulos" },
    { name: "Livretos / Agendas / Revistas", slug: "livretos" },
    { name: "Papéis Sublimáticos", slug: "papeis-sublimaticos" },
    { name: "Cartões de Visita / Crachás", slug: "crachas" },
    { name: "Embalagens", slug: "embalagens" },
    { name: "Pastas / Envelopes / Blocos", slug: "pastas" },
  ];

  const images = [
    {
      src: "/images/products/lg/agendas-revistas-livros-lg-1.png",
      category: "livretos",
      colspan2: true,
    },
    {
      src: "/images/products/pastas-envelopes-blocos-1.png",
      category: "pastas",
      colspan2: false,
    },
    {
      src: "/images/products/embalagens-1.png",
      category: "embalagens",
      colspan2: false,
    },
    {
      src: "/images/products/lg/catazes-panfletos-encartes-1.png",
      category: "panfletos",
      colspan2: true,
    },
    {
      src: "/images/products/lg/papeis-sublimaticos-1.png",
      category: "papeis-sublimaticos",
      colspan2: true,
    },
    {
      src: "/images/products/crachas-1.png",
      category: "crachas",
      colspan2: false,
    },
    {
      src: "/images/products/lg/rotulos-lg-1.png",
      category: "rotulos",
      colspan2: true,
    },
  ];

  /**
   * @param {string} category
   */
  function filterCategory(category) {
    selectedCategory = category;
  }
</script>

<section class="container px-6 py-8 mx-auto lg:py-16" id="products">
  <h3 class="text-xl font-medium text-gray-800 md:text-2xl lg:text-3xl">
    Produtos em Destaque
  </h3>

  <div
    class="flex items-center py-6 mt-4 -mx-2 overflow-x-auto whitespace-nowrap"
  >
    {#each categories as category}
      {#if category.slug === selectedCategory}
        <button
          class=" inline-flex px-4 mx-2 focus:outline-none items-center py-0.5 text-white bg-sky-500 hover:bg-sky-400 duration-300 transition-colors rounded-2xl"
          on:click={() => filterCategory(category.slug)}
          class:selected={category.slug === selectedCategory}
        >
          {category.name}
        </button>
      {:else}
        <button
          class=" inline-flex px-4 mx-2 duration-300 transition-colors hover:bg-sky-500/70 hover:text-white text-gray-500 focus:outline-none py-0.5 cursor-pointer rounded-2xl"
          on:click={() => filterCategory(category.slug)}
          class:selected={category.slug === selectedCategory}
        >
          {category.name}
        </button>
      {/if}
    {/each}
  </div>

  <div class="grid grid-cols-1 gap-10 mt-10 md:grid-cols-2 lg:grid-cols-3">
    {#each images as image}
      {#if (selectedCategory === "todos" || image.category === selectedCategory) && image.colspan2}
        <span class="transition-all duration-500 lg:col-span-2 hover:scale-105">
          <img
            class="object-cover object-top w-full rounded-lg shadow-md shadow-gray-200 h-80 xl:h-96"
            src={image.src}
            alt=""
          />
        </span>
      {:else if image.colspan2 === false && (selectedCategory === "todos" || image.category === selectedCategory)}
        <span class="transition-all duration-500 hover:scale-105">
          <img
            class="object-cover object-top w-full rounded-lg shadow-md shadow-gray-200 h-80 xl:h-96"
            src={image.src}
            alt=""
          />
        </span>
      {/if}
    {/each}
  </div>
</section>
