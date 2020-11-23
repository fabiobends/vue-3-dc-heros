<template>
  <ul>
    <li :key="index" v-for="(hero, index) in dcHeros">
      {{ hero.name }}
      <button @click="remove(index)">×</button>
    </li>
  </ul>
  <form @submit.prevent="addHero">
    <input v-model.trim="newHero" placeholder="Type new hero here" />
    <button type="submit">Add Hero</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      isDisabled: true,
      newHero: "",
      dcHeros: [
        { name: "Supergirl" },
        { name: "Flash" },
        { name: "Batman" },
        { name: "Arrow" },
        { name: "Superman" },
      ],
    };
  },
  methods: {
    addHero() {
      if (this.newHero !== "") {
        this.dcHeros.unshift({ name: this.newHero });
        this.newHero = "";
      }
    },
    remove(index) {
      this.dcHeros = this.dcHeros.filter((hero, i) => i != index);
    },
  },
  computed: {
    herosCount() {
      return this.dcHeros.length;
    },
  },
};
</script>

<style>
</style>