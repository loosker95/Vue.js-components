<template>
  <Card content="This is the name of card" />

  <card>
    <h2>Card content Header</h2>
  </card>
  <card>Card content</card>
  <card>
    <img class="nature" src="../public/nature.jpeg" alt="nature" />
  </card>
  <br />

  <Card>
    <template v-slot:header>
      <h2>Card content Header</h2>
    </template>
    <template v-slot:default>
      <h2>Card content</h2>
    </template>
    <template v-slot:footer>
      <img class="nature" src="../public/nature.jpeg" alt="nature" />
    </template>
  </Card>
  <hr />

  <button @click="showPopup = true">show popup</button>
  <Popup v-show="showPopup" @close="showPopup = false" />

  <hr />

  <Welcome name="Fabien" speudo="Fab" />
  <Welcome name="Louce" speudo="Loos" />
  <Welcome name="Kerdely" speudo="Kerd" />
  <Welcome v-bind:name="role" :speudo="country" />

  <Article title="Learn vue.js article" :like="50" :isPublished="true" />
  <ComponentA />
  <p>The name from main component is: {{ name }}</p>
</template>

<script>
import Welcome from "./components/Welcome.vue";
import Article from "./components/Article.vue";
import ComponentA from "./components/ComponentA.vue";
import Popup from "./components/Popup.vue";
import Card from "./components/Card.vue";
export default {
  name: "App",
  data() {
    return {
      role: "Software Developer",
      country: "Vietnam",
      name: "Fabien Louce Kerdely",
      showPopup: false,
    };
  },
  components: {
    Welcome,
    Article,
    ComponentA,
    Popup,
    Card,
  },
  provide() {
    return { name: this.name };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.nature {
  width: 300px;
}
</style>
