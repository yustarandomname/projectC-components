<script>
  import Container from "./Container.svelte";
  import StyledContainer from "./StyledContainer.svelte";

  export let size = "m";
  export let data = []
  export let customStyle = false;
  export let header = false

  let columns = [
    data.filter((_,index) => index % 3 == 0),
    data.filter((_,index) => index % 3 == 1),
    data.filter((_,index) => index % 3 == 2)
  ]
</script>

<style>
  .columns {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(18rem, 1fr));
    grid-gap: 0 1rem;
  }
</style>

<Container shadow={false} padding={"0em"} {header} {size}>
  <div class="columns">
    {#each columns as column}
      <div class="column">
        {#each column as item}
          {#if customStyle}
            <slot columnItem={item}></slot>
          {:else}
            <StyledContainer data={item} />
          {/if}
        {/each}
      </div>
    {/each}
  </div>
</Container>
