<template>
  <div id="app">
    <p>Preço: <span>{{preco}}</span></p>
    <p>Itens: <span>{{item}}</span></p>
    <p>Preço Total: <span>{{item * preco}}</span></p>
    <button @click="item++">Adicionar</button>
    <button @click="item--">Remover</button>
    <p>{{item ? 'Item adicionado' : 'Nenhum item adicionado'}}</p>
    
    <p>Message is: {{ message }} {{ checkbox }}</p>
    <input v-model="message" placeholder="edit me">

    <input type="checkbox" v-model="checkbox">


    <div>Picked: {{picked}}</div>
    <input type="radio" id="one" value="One" v-model="picked">
    <label for="one">One</label>
    <input type="radio" id="two" value="Two" v-model="picked">
    <label for="two">Two</label>

    <div>Selected: {{ selected }}</div>
    <select v-model="selected">
      <option disabled value="">Select one option</option>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>

    <br>
    <br>
    <p>-------------------------------</p>
    <br>
    <br>

    <select v-model="choice">
      <option v-for="option in options" v-bind:key="option" :value="option.value">
        {{option.text}}
      </option>
    </select>

    <div>Selected: {{choice}}</div>
  </div>


</template>

<script>

export default {
  data() {
    return {
      preco: 49,
      item: 0,
      message: "",
      checkbox: "",
      picked: "",
      selected: "",
      choice: "One",
      options: [
        { text: "first", value: "One" },
        { text: "second", value: "Two" }
      ]
    }
  }
};

</script>

<style>

</style>
