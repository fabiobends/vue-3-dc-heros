<template>
  <div id="content">
    <Header />
    <DCHeros />
  </div>
</template>

<script>
import Header from "./components/Header";
import DCHeros from "./components/DCHeros";

export default {
  components: {
    Header,
    DCHeros,
  },
  beforeCreate() {
    document.title = "DC Heros";
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

body {
  background-color: #e5e5e5;
}

#content {
  width: 500px;
  background-color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  width: 300px;
  margin: 0 auto;
  padding: 10px;
  border-radius: 10px;
  box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.3), -5px 5px 5px rgba(0, 0, 0, 0.3);
}

h1 {
  padding-bottom: 10px;
}

ul {
  list-style-type: none;
  background-color: #f5f5f5;
  width: 80%;
  border-radius: 10px;
  margin: 10px;
}

li {
  display: flex;
  justify-content: space-between;
  padding: 10px;
  align-items: center;
}

button {
  border: none;
  outline: none;
  padding: 10px;
  background-color: steelblue;
  border-radius: 50px;
  margin: 5px;
  color: white;
}

li button {
  background-color: crimson;
}

input {
  outline: none;
  padding: 5px;
  padding-left: 10px;
  border-radius: 50px;
}
</style>