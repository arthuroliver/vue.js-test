<template>
  <div>
    <button @click="modalAtivo = !modalAtivo">Ativar Modal</button>
    <transition name="modal">
      <div class="modal-wrapper" v-show="modalAtivo">
        <div class="modal">
          <h1>Cadastre-se</h1>
          <form>
            <label for="email">Email</label>
            <input type="email" name="email" id="email">
            <label for="password">Password</label>
            <input type="password" name="password" id="password">
            <input type="submit" value="Logar">
          </form>
        </div>
      </div>
    </transition>
  </div>

</template>

<script>
export default {
  data() {
    return {
      modalAtivo: true
    };
  }
};


</script>

<style>
  * {
    box-sizing: border-box;
  }

  .modal-wrapper {
    position: fixed;
    width: 100vw;
    height: 100vh;
    top: 0px;
    left: 0px;
    background: rgba(0, 0, 0, 0.8);
    overflow-y: scroll
  }

  .modal {
    background: #e5e5e5;
    padding: 20px;
    max-width: 400px;
    margin: 120px auto 0 auto;
    z-index: 10;
  }



  .modal-enter,
  .modal-leave-to {
    opacity: 0;
  }

  .modal-enter-active,
  .modal-leave-to {
    transition: opacity 0.5s;
  }

</style>