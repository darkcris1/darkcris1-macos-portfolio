<script lang="ts">
  export let isBeingDragged: boolean;
</script>

<section class="container">
  <header class="app-window-drag-handle" />
  <div>
    <iframe
      class:iframe-dragged={isBeingDragged}
      src="https://crisfandino.ml"
      title="macOS Web Source Code"
    />
  </div>
</section>

<style lang="scss">
  .container {
    background-color: #252526;
    padding: 1px;

    border-radius: inherit;

    display: grid;
    grid-template-rows: auto 1fr;
  }

  iframe {
    width: 100%;
    height: 100%;

    border-radius: 0 0 0.75rem 0.75rem;

    &.iframe-dragged {
      pointer-events: none;
    }
  }

  header {
    padding: 1.2rem .5rem 1.2rem;
  }

</style>
