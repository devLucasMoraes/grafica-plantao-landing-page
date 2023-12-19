<script>
  import Atendimento from "./Atendimento.svelte";
  import Contatos from "./Contatos.svelte";
  import LogoFooter from "./LogoFooter.svelte";
  import Produtos from "./Produtos.svelte";
  import Siganos from "./Siganos.svelte";

  const year = new Date().getFullYear();
</script>

<footer class="bg-white dark:bg-sky-950">
  <div class="container p-6 mx-auto">
    <div class="lg:flex">
      <div class="w-full -mx-6 lg:w-2/5">
        <div class="px-6">
          <LogoFooter />

          <p class="max-w-sm mt-2 text-gray-500 dark:text-gray-400">
            Nosso papel é dar uma ótima impressão.
          </p>
        </div>
      </div>

      <div class="mt-6 lg:mt-0 lg:flex-1">
        <div
          class="grid grid-cols-1 gap-6 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4"
        >
          <Siganos />

          <Atendimento />

          <Produtos />

          <Contatos />
        </div>
      </div>
    </div>

    <hr class="h-px my-6 bg-gray-200 border-none dark:bg-gray-700" />

    <div>
      <p class="text-center text-gray-500 dark:text-gray-400">
        © Gráfica Plantão {year} - Todos os direitos reservados
      </p>
    </div>
  </div>
</footer>
