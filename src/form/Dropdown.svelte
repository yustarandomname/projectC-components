<script>
  export let options = [{}];
  export let selected = "";
</script>

<style>
  select {
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

<select bind:value={selected}>
  {#each options as option}
    {#if option.value && option.name}
      <option value={option.value}>option.name</option>
    {:else}
      <option value={option}>{option}</option>
    {/if}
  {/each}
</select>
