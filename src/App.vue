<template>
  <div id="content">
    <Header />
    <DCHeros />
  </div>
  <Footer />
</template>

<script>
import Header from "./components/Header";
import DCHeros from "./components/DCHeros";
import Footer from "./components/Footer";

export default {
  components: {
    Header,
    DCHeros,
    Footer,
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
  box-sizing: border-box;
}

body {
  padding-top: 10px;
  font-family: "Nunito", sans-serif;
  background-color: #e5e5e5;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  height: 100vh;
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
  box-shadow: 0px 1px 1px 1px rgba(0, 0, 0, 0.03),
    0px 2px 2px 2px rgba(0, 0, 0, 0.03), 0px 4px 4px 4px rgba(0, 0, 0, 0.03),
    0px 8px 8px 8px rgba(0, 0, 0, 0.03), 0px 16px 16px 1px rgba(0, 0, 0, 0.03);
}
</style>