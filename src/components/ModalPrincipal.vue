<template>
  <div class="modal">
    <header>
      <slot name="header"></slot>
    </header>

    <main>
      <slot name="default"></slot>
    </main>

    <footer>
      <slot name="footer"></slot>
    </footer>
  </div>

</template>

<script>
  export default {
    name: "ModalPrincipal"
  }
</script>

<style>

</style>