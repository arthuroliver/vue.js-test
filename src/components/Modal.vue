<template>
  <div>
    <button @click="modalAtivo = !modalAtivo">Ativar Modal</button>
    <transition name="modal">
      <div class="modal-wrapper" v-show="modalAtivo" @click="cliqueFora">
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
  },
  methods: {
    cliqueFora({ currentTarget, target}) {
      if(currentTarget === target) this.modalAtivo = false
    }
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
    border-radius: 4px;
    top: 0px;
    left: 0px;
    background: rgba(0, 0, 0, 0.8);
    overflow-y: scroll;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  }

  .modal {
    background: #e5e5e5;
    padding: 20px;
    max-width: 400px;
    margin: 120px auto 0 auto;
    z-index: 10;
  }

  label {
    display: block;
    margin-bottom: 5px;
  }

  input, 
  button {
    width: 100%;
    border: 2px solid rgba(0, 0, 0, 0.4);
    border-radius: 2px;
    padding: 15px 10px;
    font-size: 1rem;
    margin-bottom: 20px;
  }

  input[type="submit"],
  button {
    width: 200px;
    background: #84e;
    color: white;
    text-transform: uppercase;
    font-size: 1rem;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
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