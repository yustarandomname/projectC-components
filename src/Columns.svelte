<script>
  import Button from "./Button.svelte";
  import Container from "./Container.svelte";
  import StyledContainer from "./StyledContainer.svelte";

  export let size = "m";
  export let width = "18rem";
  export let gap = "0 1rem";
  export let data = [];
  export let filtering = fase;
  export let query = "";

  let filteredData = filter(data, query);

  function filter(data, query) {
    return data.filter(d => d.content.includes(query));
  }
</script>

<style>
  .columns {
    display: grid;
  }

  .filterBar {
    display: flex;
    width: 100%;
    justify-content: flex-end;
  }
</style>

<Container shadow={false} {size}>
  {#if filtering}
    <div class="filterBar">
      <Button on:click={() => (filteredData = filter(data, query))}>⧩</Button>
    </div>
  {/if}

  <div
    class="columns"
    style="grid-template-columns: repeat(auto-fit, minmax({width}, 1fr)); {'grid-gap'}:
    {gap}">
    {#each filteredData as component}
      <StyledContainer data={component} />
    {/each}
  </div>
</Container>
