<script>
  import Input from "./Input.svelte"

  export let required = true
  export let value = ["", ""]
  export let header = false
</script>

<style>
  .datetime {
    display: flex;
    gap: 1em;
  }
</style>

<Input {header}>
  <div class="datetime">
    <input type="date" {required} bind:value={value[0]}>
    <input type="time" {required} bind:value={value[1]}>
  </div>
</Input>