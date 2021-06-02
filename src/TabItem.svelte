<script>
  import Container from "./Container.svelte"
  
  export let size = "m"
</script>

<style>
  :global(.tab > .container) {
    max-width: 100%
  }

  .tab {
    display: inline-flex;
    max-width:90vw;
  }

  .tab:not(:first-child) {
    margin-left: 1em;
  }
</style>

<div class="tab">
  <Container {size} margin="0em">
    <slot/>
  </Container> 
</div>