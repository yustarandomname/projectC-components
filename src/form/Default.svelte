<script>
  import Input from "./Input.svelte"
  export let placeholder = ""
  export let required = true
  export let value = ""
  export let type = "text"
  export let header = false

  function typeAction(node) {
		node.type = type;
	}
</script>

{#key type}
  <Input header={header}>
    <input use:typeAction {placeholder} {required} bind:value>
  </Input>
{/key}
