<template>
  <div>
    <button @click="componenteAtivo = 'sobre'">Sobre</button>
    <button @click="componenteAtivo = 'servicos'">Serviços</button>
    <transition mode="out-in">
      <component v-bind:is="componenteAtivo"></component>
    </transition>
  </div>
</template>

<script>
import sobre from "./components/Sobre.vue"
import servicos from "./components/Servicos.vue"

export default {
  components: {
    sobre,
    servicos
  },
  data() {
    return {
      componenteAtivo: "sobre"
    }
  }
};

</script>

<style>

.v-enter-active,
.v-leave-active {
  transition: opacity 0.1s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

</style>
