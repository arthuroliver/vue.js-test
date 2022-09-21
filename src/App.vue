<template>
  <div id="app">
    <modal-principal>
      <template v-slot:header>
      </template>

      <template #default>
        <button @click="abaAtiva = 'ContatoEmpresa'">Contato</button>
        <button @click="abaAtiva = 'Servicos'">Serviços</button>
        <button @click="abaAtiva = 'Sobre'">Sobre</button>

        <keep-alive>
          <component v-bind:is="abaAtiva"></component>
        </keep-alive>
      </template>

      <template v-slot:footer>
      </template>
    </modal-principal>
  </div>

</template>

<script>
  export default {
    name: "app",
    components: {
      ModalPrincipal: () => import("./components/ModalPrincipal.vue"),
      ContatoEmpresa: () => import("./components/ContatoEmpresa.vue"),
      Servicos: () => import("./components/Servicos.vue"),
      Sobre: function() {
        return import("./components/Sobre.vue");
      },
      PaginaAdministracao: function() {
        return import("./components/PaginaAdministracao.vue");
      }
    },
    data() {
      return {
        abaAtiva: "ContatoEmpresa"
      }
    }
  };

</script>

<style>

</style>
