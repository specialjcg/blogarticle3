<template>
  <div id="app">
    <Citation v-if="showComponent" @close="showComponent = false" />
    <button @click="showComponent = true">
      {{ title }}
    </button>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";
import Citation from "./components/Citation.vue";

@Component({
  components: {
    Citation
  }
})
export default class App extends Vue {
  showComponent: Boolean = false;
  title: string = "bonjour";
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
}
body {
  margin: 0;
  padding: 0;
  height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: "Lucida Console", Monaco, monospace;

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
button {
  color: #fbc831;
  font-family: "Lucida Console", Monaco, monospace;
  text-shadow: 3px 3px 3px #d17b0f;
  background: rgba(0, 113, 0, 1.2);
  background-repeat: no-repeat;
  border: none;
  cursor: pointer;
  overflow: hidden;
  outline: none;
  border-radius: 5px;
  text-decoration: none;
  height: auto;
  font-size: 2em;
  font-weight: 800;
  text-align: center;
  width: auto;
  margin-left: auto;
  margin-right: auto;
  transition: all 0.3s ease-out;
}
button:hover {
  /*background:#4BA62A;*/
  background-image: linear-gradient(
    to left,
    #007100,
    #1b7e0c,
    #2d8b17,
    #3c9821,
    #4ba62a
  );
  transition: all 0.3s ease-out;
  transform-origin: 0% 50%;
  transform: rotateY(6deg) rotateZ(1deg);
}
</style>
