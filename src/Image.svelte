<script>
  import Container from "./Container.svelte"
  import Button from "./Button.svelte"

  export let src;
  export let alt;
  export let size = "m";
  export let header;
  export let height = "25em"
  export let noStyle = true
  export let position = "center"

  let magnified = false
</script>

<style>
  img {
    border-radius: 0.6em;
    cursor: zoom-in;
    position: absolute;
    left: 50%;
    top: 1em;
    transform: translate(-50%, 0);
    transition: 0.5s height;
  }

  .left img {
    left: 0;
    transform: translate(0,0);
  }

  .right img {
    left:auto;
    right: 0;
    transform: translate(0,0);
  }

  .exitMagnified {
    position: fixed;
    left: 0;
    top: 0;
    cursor: pointer;
    background: transparent;
    transition: 0.2s background;
  }

  .magnified img {
    position: fixed;
    top:50%;
    left: 50%;
    right: auto;
    height: min(calc(100vh - 12em), 50em) !important;
    z-index: 100;
    transform: translate(-50%, -50%);
    cursor: zoom-out;
  }

  .magnified .exitMagnified {
    height:100vh;
    width: 100vw;
    z-index: 99;
    background: #56565694;
  }

  .exitButton {
    position: fixed;
    right: 10em;
    top: calc((100vh - min(calc(100vh - 12em), 50em)) / 2);
    background:white;
    border-radius: 0.6em;
    z-index: 101;
  }

  p { color: #ccc; }
</style>

<Container {size} {header} {noStyle}>
  <div style="height: calc({height})" class="imageContainer" class:magnified class:left={position == "left"} class:right={position == "right"}>
    <div class="exitMagnified" on:click={() => {magnified = false}} />

    {#if magnified}
      <div class="exitButton">
        <Button on:click={() => {magnified = false}} icon="close-outline" />
      </div>
    {/if}

    <img style="height:{height};" {src} {alt} on:click={() => {magnified = !magnified}} />
  </div>
  <p style="text-align: {position}">{alt}</p>
</Container>  

