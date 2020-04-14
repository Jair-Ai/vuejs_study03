<template>
  <div id="app">
    <div>Hello World!</div>
    <br />
    <label>Nome</label>
    <input type="text" name="name" v-model="name" />
    <label>Sobrenome</label>
    <input type="text" name="lastname" v-model="lastName" />
    <div>{{ name }} {{ lastName }}</div>
    <button @click="counting">+</button>
    <button @click="decrement">-</button>
    <div>Contador: {{ counter }}</div>
    <div v-if="counter > 5">o Contador é maior que 5</div>
    <ul>
      <li v-for="number in numbers" v-bind:key="number">{{ number }}</li>
    </ul>
    <button @click="newNumber"></button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "Alefe",
      lastName: "Souza",
      counter: 0,
      numbers: [0, 2, 6, 45, 7, 154, 153]
    };
  },
  methods: {
    counting() {
      this.counter += 1;
    },
    decrement() {
      this.counter -= 1;
    },
    newNumber() {
      this.numbers.push(Math.random());
    }
  },
  mounted() {
    setTimeout(() => {
      this.lastName = "França";
    }, 2000);

    setInterval(() => {
      this.name = "Maria";
      console.log(this.name);
    }, 1000);
  }
};
</script>
<style scoped></style>
