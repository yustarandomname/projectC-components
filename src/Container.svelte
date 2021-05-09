<script>
  export let size = "full";
  export let width = null;
  export let background = false;
  export let borderColor = false;
  export let shadow = true;
  export let margin = "0 auto 1rem auto";
  export let padding = false
  export let header = false
  export let hoverable = false
  export let highlight = false
  export let overflow = false
</script>

<style>
  .container {
    width: 100%;
    max-width: min(90vw, 100%);
    position: relative;
    overflow: hidden;
    border-radius: 0.6rem;
    box-sizing: border-box;
    padding: 0.75rem;
    border: 1px solid transparent;
  }

  .withHeader {
    margin-top: 2.5rem !important;
    overflow: visible;
  }
  .withHeader:before {
    content: attr(header);
    position: absolute;
    top: -1.8rem;
    left: 0;
    font-weight: bold;
    font-size: 1.3rem;
}

  .shadow {
    box-shadow: 0.1rem 0.1rem 1rem rgb(0 0 0 / 10%);
  }


  .hoverable { box-shadow: 0 0 0.5rem rgb(0 0 0 / 10%); cursor:pointer; transition: 0.2s; }
  .hoverable:hover,
  .highlight { box-shadow: 0 0 .5rem rgb(0 0 0 / 30%); }

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
    class="container {size}-size" class:hoverable class:highlight class:withHeader={header} {header}
    class:shadow
    style="background: {background}; margin: {margin}; padding: {padding}; width: {width};
    border-color: {borderColor}; overflow: {overflow}" on:click>
    <slot />
  </div>