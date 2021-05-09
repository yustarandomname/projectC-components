<script>
  import Container from "../Container.svelte"

  export let size = "m"
  export let header = false
  export let submitMessage = "Submit form"
  export let error = false;
  export let feedback = false;
</script>

<style>
  .positionSubmit {
    display: flex;
    justify-content: flex-end;
  }

  .submit {
    all: inherit;
    margin: 0.8em 0 0 0;
    width: fit-content;
    padding: 0.5em 1em;
    border: 1px solid #555;
    border-radius: 0.6em;
    cursor: pointer;
    user-select:none;
  }

  /* Feedback */
  .error,
  .feedback {
    font-size: 0.75em;
    text-align: right;
  }

  .error { color: red;}
  .feedback { color: green;}

</style>

<Container {size} {header}>
  <form on:submit|preventDefault>
    <slot/>

    {#if feedback}
      <div class="feedback">{feedback}</div>
    {:else if error}
      <div class="error">{error}</div>
    {/if}

    {#if submitMessage}
      <div class="positionSubmit" >
        <button type="submit" class="submit">
          <slot name="submit">{submitMessage}</slot> 
        </button>
      </div>
    {/if}
  </form>
</Container>
