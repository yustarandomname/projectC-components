<script>
  import Container from "../Container.svelte"

  export let size = "m"
  export let header = false
  export let submitMessage = "Submit form"
</script>

<style>
  .positionSubmit {
    display: flex;
    justify-content: flex-end;
  }

  .submit {
    all: inherit;
    margin: 0;
    width: fit-content;
    padding: 0.5em 1em;
    border: 1px solid #555;
    border-radius: 0.6em;
    cursor: pointer;
  }
</style>

<Container {size} {header}>
  <form on:submit|preventDefault>
    <slot/>
    <div class="positionSubmit" >
      <button type="submit" class="submit">
        <slot name="submit">{submitMessage}</slot> 
      </button>
    </div>
  </form>
</Container>
