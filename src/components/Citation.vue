<template>
  <transition name="fade" @after-enter="essai()">
    <div class="fond" @click="showContent = false">
      <transition name="fade" @after-leave="$emit('close')">
        <div v-if="showContent" class="content" @click.stop>
          {{ Alea }}
        </div>
      </transition>
    </div>
  </transition>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component({})
export default class Citation extends Vue {
  Alea: String = "";
  showContent: Boolean = false;
  numbre: number = 0;
  citationtext: Array<string> = [
    "Exige beaucoup de toi-même et attends peu des autres. Ainsi beaucoup d'ennuis te seront épargnés.Confucius",
    "Dans la vie on ne fait pas ce que l'on veut mais on est responsable de ce que l'on est.Jean Paul Sartre",
    "La vie est un mystère qu'il faut vivre, et non un problème à résoudre.Gandhi",
    "On a deux vies. La deuxième commence quand on réalise qu’on n’en a qu’une. Confucius",
    "« Si vous pouvez le rêver, vous pouvez le faire. » Walt Disney",
    "Si vous pensez que l’aventure est dangereuse, essayez la routine, elle est mortelle. » Paulo Coelho",
    "« Un voyage de mille lieues commence toujours par un premier pas. » Lao Tseu",
    "« J’ai des questions à toutes vos réponses »  Woody Allen ",
    "« Les autres parlent, moi je travaille »picasso"
  ];
  mounted() {
    this.Alea = this.citationtext[Math.floor(Math.random() * 9)];
    window.setInterval(() => {
      this.numbre = Math.floor(Math.random() * 9);
      this.Alea = this.citationtext[this.numbre];
    }, 2000);
  }
  essai() {
    this.showContent = true;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
  transition: 0.2s opacity ease-out;
}

.fond {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.6);
  z-index: 1;
}
.content {
  position: absolute;
  top: 50%;
  left: 50%;
  width: calc(100% - 20px);
  max-width: 500px;
  transform: translate(-50%, -50%);
  background: #fff;
  border-radius: 3px;
  padding: 20px;
  line-height: 1.5;
  font-size: 18px;
  color: #444;
  box-shadow: -2rem 2rem 2rem rgba(black, 0.2);
}
</style>
