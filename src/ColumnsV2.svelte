<script>
  import Button from "./Button.svelte";
  import Container from "./Container.svelte";
  import StyledContainer from "./StyledContainer.svelte";

  export let size = "m";
  export let data = []
  export let defaultStyle = true;

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

<Container shadow={false} {size}>
  <div class="columns">
    {#each columns as column}
      <div class="column">
        {#each column as item}
          {#if defaultStyle}
            <StyledContainer data={item} />
          {:else}
            <slot columnItem={item}></slot>
          {/if}
        {/each}
      </div>
    {/each}
  </div>
</Container>
