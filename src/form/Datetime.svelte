<script>
  export let required = true
  export let value = ["", ""]
</script>

<style>
  .datetime {
    display: flex;
    gap: 1em;
  }

  input {
    all: inherit;
    margin: 0.8em 0 0.2em;
    width: calc(100% - 2em - 2px);
    padding: 0.5em 1em;
    border: 1px solid #555;
    border-radius: 0.6em;
    cursor: pointer;
  }
</style>

<div class="datetime">
  <input type="date" {required} bind:value={value[0]}>
  <input type="time" {required} bind:value={value[1]}>
</div>