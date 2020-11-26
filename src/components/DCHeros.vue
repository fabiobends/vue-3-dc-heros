<template>
  <ul>
    <li
      :key="index"
      v-for="(hero, index) in dcHeros"
      :class="animate ? 'animate-child' : ''"
    >
      {{ hero.name }}
      <button @click="remove(index)">×</button>
    </li>
  </ul>
  <form @submit.prevent="addHero" class="footer-card">
    <input
      v-model.trim="newHero"
      placeholder="Type new hero here"
      @keydown="animate = False"
    />
    <button type="submit" class="confirm">Add Hero</button>
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
      animate: false,
      opaque: false,
    };
  },
  methods: {
    addHero() {
      if (this.newHero !== "") {
        this.dcHeros.unshift({ name: this.newHero });
        this.newHero = "";
        this.animate = true;
      }
    },
    remove(index) {
      this.dcHeros = this.dcHeros.filter((hero, i) => i != index);
      this.opaque = true;
    },
  },
  computed: {
    herosCount() {
      return this.dcHeros.length;
    },
  },
};
</script>

<style scoped>
h1 {
  padding-bottom: 10px;
}

ul {
  list-style-type: none;
  background-color: #f5f5f5;
  width: 80%;
  border-radius: 10px;
  margin: 10px;
  box-shadow: 0px 1px 1px 1px rgba(0, 0, 0, 0.03),
    0px 2px 2px 2px rgba(0, 0, 0, 0.03), 0px 4px 4px 4px rgba(0, 0, 0, 0.03),
    0px 8px 8px 8px rgba(0, 0, 0, 0.03);
}

li {
  display: flex;
  justify-content: space-between;
  padding: 10px;
  align-items: center;
}

.animate-child:nth-child(1) {
  animation: shift 0.5s 1 ease-in;
  background-color: #f5f5f5;
  border-radius: 10px;
}

@keyframes shift {
  0% {
    transform: translateX(-10%);
  }
  50% {
    transform: translateX(20%);
  }
  100% {
    transform: translateX(-10%);
  }
}

button {
  border: none;
  outline: none;
  padding: 10px;
  border-radius: 10px;
  color: white;
}

li button {
  height: 30px;
  width: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: crimson;
  box-shadow: 0px 1px 1px 1px rgba(0, 0, 0, 0.15),
    0px 2px 2px 2px rgba(0, 0, 0, 0.15), 0px 4px 4px 0px rgba(0, 0, 0, 0.15);
  transition: 0.2s all ease-in;
}

li button:hover {
  background: white;
  color: crimson;
  border: 2px solid crimson;
}

.confirm {
  background-color: steelblue;
  box-shadow: 0px 1px 1px 1px rgba(0, 0, 0, 0.03),
    0px 2px 2px 2px rgba(0, 0, 0, 0.03), 0px 4px 4px 4px rgba(0, 0, 0, 0.03),
    0px 8px 8px 8px rgba(0, 0, 0, 0.03);
  transition: 0.2s filter ease-in;
}

.confirm:hover {
  filter: brightness(130%);
}

.footer-card {
  display: flex;
  justify-content: space-between;
  width: 90%;
  margin-top: 10px;
}

input {
  outline: none;
  border: 1px solid grey;
  padding: 7px;
  padding-left: 10px;
  border-radius: 5px;
  box-shadow: inset 0px 1px 1px 1px rgba(0, 0, 0, 0.03),
    inset 0px 2px 2px 2px rgba(0, 0, 0, 0.03),
    inset 0px 4px 4px 2px rgba(0, 0, 0, 0.03),
    inset 0px -1px 1px 1px rgba(0, 0, 0, 0.03),
    inset 0px -2px 2px 2px rgba(0, 0, 0, 0.03),
    inset 0px -4px 4px 2px rgba(0, 0, 0, 0.03);
}

input:focus {
  border: 2px solid steelblue;
}

@media screen and (max-width: 600px) {
  .footer-card {
    flex-direction: column;
    width: 80%;
  }

  input {
    margin-bottom: 10px;
    padding: 15px;
  }

  .confirm {
    padding: 15px;
    transition: 0.1s all ease-in;
  }

  .confirm:focus {
    filter: none;
  }

  .confirm:active {
    border: 2px solid steelblue;
    background: white;
    color: steelblue;
  }

  li button:hover {
    background: crimson;
    color: white;
    border: none;
  }

  li button:active {
    background: white;
    color: crimson;
    border: 2px solid crimson;
  }

}
</style>