<script>
  import Input from "./Input.svelte"

  export let options = [{}];
  export let selected = "";
  export let header = false
</script>

<Input {header}>
  <select bind:value={selected}>
    {#each options as option}
      {#if option.value && option.name}
        <option value={option.value}>option.name</option>
      {:else}
        <option value={option}>{option}</option>
      {/if}
    {/each}
  </select>
</Input>
