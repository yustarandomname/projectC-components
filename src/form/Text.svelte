<script>
  export let placeholder = ""
  export let required = true
  export let value = "test123"
</script>

<style>
  input {
    all: inherit;
    margin: 0;
    width: fit-content;
    padding: 0.5em 1em;
    border: 1px solid #555;
    border-radius: 0.6em;
    cursor: pointer;
    margin-bottom: 1em;
  }
</style>

<input type="text" {placeholder} {required} bind:value>