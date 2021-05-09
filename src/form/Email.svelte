<script>
  import Icon from "../Icon.svelte"

  export let placeholder = "Email"
  export let required = true
  export let value = ""
  export let autocomplete = "username"
  export const type = "email"
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

  .email {position: relative; }
  .clear {
    position: absolute;
    right: 0.5em;
    height: 100%;
    top: 0.4em;
    cursor: pointer;
  }
</style>

<div class="email">
  <input type="email" {placeholder} {required} {autocomplete} bind:value>
  <div class="clear" on:click={() => value = ""}>
    <Icon name="close-outline"></Icon>
  </div>
</div>
