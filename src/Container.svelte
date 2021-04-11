<script>
  export let size = "full";
  export let width = null;
  export let background = "transparent";
  export let borderColor = "transparent";
  export let shadow = true;
  export let margin = "1rem auto";
</script>

<style>
  .container {
    width: 100%;
    max-width: min(90vw, 100%);
    position: relative;
    border-radius: 0.6rem;
    box-sizing: border-box;
    overflow: hidden;
    padding: 0.75rem;
    border: 1px solid transparent;
  }

  .shadow {
    box-shadow: 0.1rem 0.1rem 1rem rgb(0 0 0 / 10%);
  }

  .extra-small-size,
  .xs-size {
    width: 20rem;
  }
  .small-size,
  .s-size {
    width: 40rem;
  }
  .medium-size,
  .m-size {
    width: 60rem;
  }
  .large-size,
  .l-size {
    width: 80rem;
  }
  .extra-large-size,
  .xl-size {
    width: 100rem;
  }
</style>

<div
  class="container {size}-size"
  class:shadow
  style="background: {background}; margin: {margin}; width: {width};
  border-color: {borderColor}">
  <slot />
</div>
