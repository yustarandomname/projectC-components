<script>
  export let header = false
  export let footer = false
</script>

<style>
  .multiInput {
    position: relative;
    display: flex;
    gap: 1em;
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
</style>

<div class="multiInput" class:header class:footer data-header={header} data-footer={footer}>
  <slot />
</div>