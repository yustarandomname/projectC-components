<script>
  export let placeholder = ""
  export let required = true
  export let value = ""
  export let type = "text"

  function typeAction(node) {
		node.type = type;
	}
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
</style>

{#key type}
  <input use:typeAction {placeholder} {required} bind:value>
{/key}
