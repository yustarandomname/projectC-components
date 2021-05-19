<script>
  export let header = false
</script>

<style>
  div {
    position: relative;
    margin: 0.8em 0 0.2em;
  }

  .header { margin-top:1.4em; }

  .header::before {
    content: attr(data-header);
    font-size: 0.5em;
    font-weight: bold;
    color: #555;
    position: absolute;
    top: -1.4em;
    left: 0.6em;
    text-transform: uppercase;
  }

  :global(input),
  :global(select) {
    all: inherit;
    width: calc(100% - 2em - 2px);
    padding: 0.5em 1em;
    border: 1px solid #555;
    border-radius: 0.6em;
    cursor: pointer;
  }

  :global(select) {
    width: fit-content;
  }
</style>

<div class:header data-header={header}>
  <slot/>
</div>