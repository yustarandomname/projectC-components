<script>
  export let header = false
  export let footer = false
</script>

<style>
  div {
    position: relative;
    margin: 0.8em 0 0.2em;
    width: 100%;
  }

  .header { margin-top:1.4em; }
  .footer { margin-bottom: 2em}

  .header::before,
  .footer::after {
    color: #555;
    position: absolute;
    left: 0.6em;
  }

  .header::before {
    font-size: 0.5em;
    content: attr(data-header);
    top: -1.4em;
    font-weight: bold;
    text-transform: uppercase;
  }

  .footer::after {
    font-size: 0.7em;
    content: attr(data-footer);
    bottom: -1.2em;
    text-transform: lowercase;
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

<div class:header class:footer data-header={header} data-footer={footer}>
  <slot/>
</div>