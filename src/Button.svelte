<script>
  import Container from "./Container.svelte";
  import Icon from "./Icon.svelte"

  export let background = "transparent";
  export let borderColor = "transparent";
  export let padding = "0.75em"
  export let margin = "0";
  export let icon = false
</script>

<style>
  button {
    all: unset;
    height: 3rem;
    width: fit-content;
    cursor: pointer;
    outline: none;
    background: transparent !important
  }

  .center {
    display: grid;
    place-items: center;
  }
</style>

<button on:click>
  <Container {background} shadow={false} {borderColor} {padding} {margin} hoverable={true}>
    <div class="center">
      {#if icon}
        <Icon name={icon} />
      {:else}
        <slot />
      {/if}
    </div>
  </Container>
</button>
