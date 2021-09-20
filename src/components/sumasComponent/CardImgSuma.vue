<template>
  <q-card
    class="my-card row justify-center"
    style="background-color: rgb(0,0,0,0.0)"
  >
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
