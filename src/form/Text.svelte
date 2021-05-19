<script>
  import Input from "./Input.svelte"

  export let placeholder = ""
  export let required = true
  export let value = ""
  export let header = false
</script>

<Input {header}>
  <input type="text" {placeholder} {required} bind:value>
</Input>