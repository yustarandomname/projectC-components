<script>
  import Icon from "../Icon.svelte"

  export let placeholder = "password"
  export let required = true
  export let value = ""
  export let autocomplete = "current-password"
  export let pattern=".*"

  let visible = false
</script>

<style>
  input {
    all: inherit;
    margin: 0.8em 0 0.2em;
    width: calc(100% - 2em - 2px);
    padding: 0.5em 1em;
    border: 1px solid #555;
    border-radius: 0.6em;
    cursor: pointer;
  }

  .password {position:relative}
  .visibility {
    position: absolute;
    right: 0.5em;
    height: 100%;
    top: 0.4em;
    cursor: pointer;
  }
</style>

<svelte:window on:mouseup={() => visible = false}></svelte:window>

<div class="password">

  {#if visible}
    <input hidden type="text" {placeholder} {required} bind:value />
  {:else}
  <input type="hidden" autocomplete="username">

    <input type="password" {placeholder} {required} {autocomplete} {pattern} bind:value />
  {/if}
  <div class="visibility" on:mousedown={() => visible = true}><Icon name={(visible) ? "eye-off-outline" : "eye-outline"}/></div>
</div>
