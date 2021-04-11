<script>
  export let options = [{}];
  export let selected = "";
</script>

<select bind:value={selected}>
  {#each options as option}
    {#if option.value && option.name}
      <option value={option.value}>option.name</option>
    {:else}
      <option value={option}>{option}</option>
    {/if}
  {/each}
</select>
