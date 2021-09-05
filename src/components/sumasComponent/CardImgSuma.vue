<template>
  <q-card
    class="my-card row justify-center"
    style="background-color: rgb(0,0,0,0.0)"
  >
    <audio id="Red"><source src="Colores/Red.mp3" /></audio>
    <audio id="Blue"><source src="Colores/Blue.mp3" /></audio>
    <audio id="Yellow"><source src="Colores/Yellow.mp3" /></audio>
    <audio id="Green"><source src="Colores/Green.mp3" /></audio>
    <audio id="Orange"><source src="Colores/Orange.mp3" /></audio>
    <audio id="Purple"><source src="Colores/Purple.mp3" /></audio>
    <audio id="Grey"><source src="Colores/Grey.mp3" /></audio>
    <audio id="Pink"><source src="Colores/Pink.mp3" /></audio>
    <audio id="White"><source src="Colores/White.mp3" /></audio>

    <q-img 
      style="width: 250px; height: 250px; border-radius: 50%"
      :src="imagen"
      basic
      class="row justify-center"
    >
      <div class="absolute-bottom column justify-center">
        <div class="text-h6">
          <strong :class="'text-' + color">{{ textoIngles }}</strong>
        </div>
        <p>{{ textoEspaniol }}</p>
        <q-btn
          @click="crearAudio(audio)"
          class="self-center shadow-24"
          :color="color"
          push
          
          icon="campaign"
          :class="color === 'white' ? 'text-black' : 'text-white'"
        ></q-btn>
      </div>
    </q-img>
  </q-card>
</template>

<script>
export default {
  data() {
    return {};
  },

  methods: {
    crearAudio(sound) {
      var number = document.getElementById(sound);
      number.play();
      console.log(sound);
    }
  },

  props: {
    imagen: {
      type: String,
      required: true,
      default: "img/colors_grey.jpg"
    },

    color: {
      type: String,
      default: "text-white"
    },

    textoIngles: {
      type: String,
      default: "The cat is GRAY"
    },

    textoEspaniol: {
      type: String,
      default: "El gato es gris"
    },

    audio: {
      type: String,
      default: "grey"
    }
  }
};
</script>

<style lang="sass" scoped>
.my-card
    width: 100%
    max-width: 250px
</style>
