<script>
  const contatos = [
    {
      nome: "Orçamento",
      numero: "75 99264-1598",
      email: "orcamento@graficaplantao.com",
    },
    {
      nome: "Cartões de visita",
      numero: "75 3626-6591",
      email: "cartao@graficaplantao.com",
    },
    {
      nome: "Financeiro",
      numero: "75 8848-4864",
      email: "financeiro@graficaplantao.com",
    },
    {
      nome: "Entrega",
      numero: "75 3223-4315",
      email: "",
    },
  ];
</script>

<div>
  <h3 class=" uppercase text-white">Contatos</h3>
  {#each contatos as { nome, numero, email }}
    <h3 class=" uppercase text-white text-xs mt-2">
      {nome}
    </h3>
    <span class="block mt-2 text-sm text-gray-400 hover:underline"
      >{numero}</span
    >
    <span class="block mt-2 text-sm text-gray-400 hover:underline">{email}</span
    >
  {/each}
</div>
