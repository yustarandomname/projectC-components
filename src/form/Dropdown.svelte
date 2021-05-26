<script>
  import Input from "./Input.svelte"

  export let options = [{}];
  export let value = "";
  export let header = false
  export let footer = false
</script>

<Input {header} {footer}>
  <select bind:value>
    {#each options as option}
      {#if option.value && option.name}
        <option value={option.value}>option.name</option>
      {:else}
        <option value={option}>{option}</option>
      {/if}
    {/each}
  </select>
</Input>
