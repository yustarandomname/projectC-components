<script>
  import Container from "./Container.svelte";

  export let background = "transparent";
  export let borderColor = "transparent";
  export let margin = "0";
</script>

<style>
  .button {
    height: 3rem;
    width: 3rem;
    cursor: pointer;
  }

  .center {
    display: grid;
    place-items: center;
  }
</style>

<div class="button" on:click>
  <Container {background} {borderColor} {margin}>
    <div class="center">
      <slot />
    </div>
  </Container>
</div>
