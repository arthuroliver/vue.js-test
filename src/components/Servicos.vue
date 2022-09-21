<template>
  <div>
    <h1>Serviços</h1>
    <button @click="abaAtiva = 'PaginaAdministracao'">Administração</button>
    <keep-alive>
      <component :is="abaAtiva"></component>
    </keep-alive>
  </div>

</template>

<script>

  export default {
    name: "Serviço",
    data() {
      return {
        abaAtiva: "PaginaAdministracao"
      }
    }
  };
</script>

<style>

</style>