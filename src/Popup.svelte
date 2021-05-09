<script>
  import { createEventDispatcher } from 'svelte';

  import Container from "./Container.svelte"
  import Button from "./Button.svelte"
  export let show = false
  export let size = "s"

  const dispatch = createEventDispatcher()

  const exit = () => dispatch('exit');
</script>

<style>
  .exitPopup {
    position: fixed;
    left: 0;
    top: 0;
    width: 100vw;
    height: 100vh;
    z-index: 1000;
  }

  .exitPopup {
    background: #56565694;
    cursor: pointer;
  }

  .popupContainer {
    position: fixed;
    z-index: 1000;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    max-height: 80vh;
  }

  .popup {
    position: relative;
  }

  .exitButton {
    position: absolute;
    right: -1.5rem;
    top: -1.5rem;
    background:white;
    border-radius: 0.6em;
    z-index: 1;
  }
</style>

{#if show}
  <div class="exitPopup" on:click={exit} />
  <div class="popupContainer">
    <div class="popup">
      <div class="exitButton">
        <Button on:click={exit} icon="close-outline" />
      </div>
      <Container {size} shadow={false} background="white">
        <slot />
      </Container>
    </div>
  </div>  
{/if}