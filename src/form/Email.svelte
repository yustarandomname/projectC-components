<script>
  import Input from "./Input.svelte"
  import Icon from "../Icon.svelte"

  export let placeholder = "Email"
  export let required = true
  export let value = ""
  export let autocomplete = "username"
  export let header = "email"
</script>

<style>
  .clear {
    position: absolute;
    right: 0.5em;
    height: 100%;
    top: 0.4em;
    cursor: pointer;
  }
</style>

<Input {header}>
  <input type="email" {placeholder} {required} {autocomplete} bind:value>
  <div class="clear" on:click={() => value = ""}>
    <Icon name="close-outline"></Icon>
  </div>
</Input>
