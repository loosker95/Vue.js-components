<template>
  <!-- Dynamic component -->
  <button @click="show = 'TabA'">Tab A</button>
  <button @click="show = 'TabB'">Tab B</button>
  <button @click="show = 'TabC'">Tab C</button>

  <keep-alive>
    <component :is="show" />
  </keep-alive>
  <!-- <TabA v-if="show === 'TabA'" />
  <TabB v-if="show === 'TabB'" />
  <TabC v-if="show === 'TabC'" /> -->

  <hr />
  <Card content="This is the name of card" />
  <card>
    <h2>Card content Header</h2>
  </card>
  <card>Card content</card>
  <card>
    <img class="nature" src="../public/nature.jpeg" alt="nature" />
  </card>
  <br />

  <!-- Slot name -->
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

  <!-- Event emit -->
  <button @click="showPopup = true">show popup</button>
  <Popup v-show="showPopup" @close="showPopup = false" />

  <hr />

  <!-- Component props -->
  <Welcome name="Fabien" speudo="Fab" />
  <Welcome name="Louce" speudo="Loos" />
  <Welcome name="Kerdely" speudo="Kerd" />
  <Welcome v-bind:name="role" :speudo="country" />

  <Article title="Learn vue.js article" :like="50" :isPublished="true" />
  <ComponentA />
  <p>The name from main component is: {{ name }}</p>

  <hr />
  <!-- Teleport component -->
  <teleport to="#modal">
    <Portal />
  </teleport>
</template>

<script>
import Welcome from "./components/Welcome.vue";
import Article from "./components/Article.vue";
import ComponentA from "./components/ComponentA.vue";
import Popup from "./components/Popup.vue";
import Card from "./components/Card.vue";
import TabA from "./components/TabA.vue";
import TabB from "./components/TabB.vue";
import TabC from "./components/TabC.vue";
import Portal from "./components/Portal.vue";
export default {
  name: "App",
  data() {
    return {
      role: "Software Developer",
      country: "Vietnam",
      name: "Fabien Louce Kerdely",
      showPopup: false,
      show: "TabA",
    };
  },
  components: {
    Welcome,
    Article,
    ComponentA,
    Popup,
    Card,
    TabA,
    TabB,
    TabC,
    Portal,
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
