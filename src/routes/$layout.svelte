<script type="ts">
  import "./_global.pcss";

  let active: boolean = false;
</script>

<div class="w-full">
  <navbar class="w-full border-b flex justify-center p-3">
    <div class="container flex">
      <div class="flex flex-wrap justify-between md:justify-start w-full">
        <a class="text-2xl mx-5 p-2" href="/">Sebastian</a>
        <button
          class="md:hidden flex items-center px-3 py-2 rounded"
          on:click={() => (active = !active)}
        >
          <svg
            class="h-3 w-3"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
            ><title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" /></svg
          >
        </button>
        <div class="{active ? "flex flex-wrap flex-col flex-basis" : "hidden"} md:flex md:flex-row md:items-center text-center">
          <a href="/transaction" class="menu-item">Transaction</a>
          <a href="/budget" class="menu-item"> Budget</a>
          <a href="/source" class="menu-item">Source</a>
        </div>
      </div>
    </div>
  </navbar>

  <slot />
</div>

<style type="postcss">
  .menu-item {
    @apply p-2;
    @apply mx-2;
  }
  .menu-item:hover {
    background-color: rgb(246, 246, 246);
  }

  .flex-basis {
    flex-basis: 100%;
  }
</style>
