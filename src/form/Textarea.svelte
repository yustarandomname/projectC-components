<script>
  export let placeholder = ""
  export let required = true
  export let minRows = 4;
	export let maxRows = 10;
  export let value = ""

  $: minHeight = `${1 + minRows * 1.2}em`;
	$: maxHeight = maxRows ? `${1 + maxRows * 1.2}em` : `auto`;
</script>

<style>
	.container {
		position: relative;
	}
	
	pre, textarea {
		font-family: inherit;
		padding: 0.5em;
		box-sizing: border-box;
		border: 1px solid #eee;
		line-height: 1.2;
		overflow: auto;
	}
	
	textarea {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		resize: none;
    outline: none;
    border: 1px solid #555;
    border-radius: 0.6em;
	}
</style>

<div class="container">
	<pre
		aria-hidden="true"
		style="min-height: {minHeight}; max-height: {maxHeight}"
	>{value + '\n'}</pre>

	<textarea type="text" {placeholder} {required} bind:value></textarea>
</div>

