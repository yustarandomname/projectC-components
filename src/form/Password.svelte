<script>
  import Icon from "../Icon.svelte"
  import Input from "./Input.svelte"

  export let placeholder = "password"
  export let required = true
  export let value = ""
  export let autocomplete = "current-password"
  export let pattern=".*"
  export let header = "password"

  let visible = false
</script>

<style>
  .visibility {
    position: absolute;
    right: 0.5em;
    height: 100%;
    top: 0.4em;
    cursor: pointer;
  }
</style>

<svelte:window on:mouseup={() => visible = false}></svelte:window>

<Input {header}>

  {#if visible}
    <input hidden type="text" {placeholder} {required} bind:value />
  {:else}
    <input type="password" {placeholder} {required} {autocomplete} {pattern} bind:value />
  {/if}
  <div class="visibility" on:mousedown={() => visible = true}><Icon name={(visible) ? "eye-off-outline" : "eye-outline"}/></div>
</Input>
