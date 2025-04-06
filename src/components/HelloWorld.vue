<template>
  <div>
    <h2>{{ title }}</h2>
    <button @click="increment">Cliquei {{ count }} vezes</button>
  </div>
</template>

<script>
export default {
  props: ["title"], // Propriedade recebida do componente pai
  data() {
    return {
      count: 0
    };
  },
  methods: {
    increment() {
      this.count++;
    }
  }
};
</script>

<style scoped>
button {
  background-color: blue;
  color: white;
  padding: 10px;
  border-radius: 5px;
}
</style>