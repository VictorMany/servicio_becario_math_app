<template>
  <div
    class="q-pa-md"
    style="
      width: 100%;
      height: 90%;
      background-color: rgb(10, 10, 10, 0.8);
      overflow: scroll;
    "
  >
    <h4
      style="
        margin-top: -0.3rem;
        margin-bottom: 2rem;
        width: 100%;
        padding: 0.4rem;
        border-radius: 0.5rem;
        align: center;
        font-weight: bold;
      "
      class="bg-blue-13 text-white text-center"
    >
      Sumas
    </h4>

    <div>
      <div class="row">
        <div
          class="col bg-blue-13"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="crearAudio('blue')"
        />
        <div
          class="col bg-white"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="crearAudio('white')"
        />
        <div
          class="col bg-red-13"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="crearAudio('red')"
        />
      </div>
      <q-img
        src="https://www.orientacionandujar.es/wp-content/uploads/2016/01/vamos-a-sumar-con-los-dedos-2.jpg"
      ></q-img>
      <div class="row">
        <div
          class="col bg-purple"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="crearAudio('purple')"
        />
        <div
          class="col bg-green-14"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="crearAudio('green')"
        />
        <div
          class="col bg-orange-10"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="crearAudio('orange')"
        />
      </div>
      <div class="row">
        <div
          class="col bg-yellow-13"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="crearAudio('yellow')"
        />
        <div
          class="col bg-pink"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="crearAudio('pink')"
        />
        <div
          class="col bg-grey-7"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="crearAudio('grey')"
        />
      </div>
    </div>

    <div
      style="margin-top: 2rem; margin-bottom: 1rem"
      class="row justify-center"
    >
      <card-img-suma
        class="color-card"
        :imagen="imagen"
        :color="color"
        :audio="audio"
        :textoEspaniol="textoEspaniol"
        :textoIngles="textoIngles"
      ></card-img-suma>
    </div>

    <q-btn
      push
      style="height: 40px; width: 100%; margin-top: 1rem"
      label="CLOSE"
      color="red-10"
      v-close-popup
      ><p style="font-size: 0.5rem; margin-left: 0.5rem">(Cerrar)</p></q-btn
    >
  </div>
</template>

<script>
import CardImgSuma from "./CardImgSuma.vue";
export default {
  components: { CardImgSuma },
  created() {
    this.imagen = "img/colors_grey.jpg";
    this.color = "grey-13";
    this.textoEspaniol = "El gato es gris";
    this.audio = "Grey";
    this.textoIngles = "The cat is GREY";
  },
  data() {
    return {
      numbers_0_20: false,
      numbers_tens: false,
      numbers_hundreds: false,
      numbers_thousands: false,
      text: "",
      ph: "",

      arrayImagesColors: [
        {
          id: 1,
          imagen: "img/colors_red.png",
          color: "red-13",
          textoEspaniol: "La flor es roja",
          audio: "Red",
          textoIngles: "The flower is RED",
        },
        {
          id: 2,
          imagen: "img/colors_yellow.jpg",
          color: "yellow-13",
          textoEspaniol: "El sol es amarillo",
          audio: "Yellow",
          textoIngles: "The sun is YELLOW",
        },
        {
          id: 3,
          imagen: "img/colors_blue.jpg",
          color: "blue-13",
          textoEspaniol: "El cielo es azul",
          audio: "Blue",
          textoIngles: "The sky is BLUE",
        },
        {
          id: 4,
          imagen: "img/colors_green.jpg",
          color: "green-13",
          textoEspaniol: "El pasto es verde",
          audio: "Green",
          textoIngles: "The grass is GREEN",
        },
        {
          id: 5,
          imagen: "img/colors_orange.jpg",
          color: "orange",
          textoEspaniol: "La fruta es anaranjada",
          audio: "Orange",
          textoIngles: "The fruit is ORANGE",
        },
        {
          id: 6,
          imagen: "img/colors_purple.jpg",
          color: "purple",
          textoEspaniol: "El Minion es morado",
          audio: "Purple",
          textoIngles: "The Minion is PURPLE",
        },
        {
          id: 7,
          imagen: "img/colors_grey.jpg",
          color: "grey",
          textoEspaniol: "El gato es gris",
          audio: "Grey",
          textoIngles: "The cat is GREY",
        },
        {
          id: 8,
          imagen: "img/colors_pink.jpg",
          color: "pink",
          textoEspaniol: "La flor es rosa",
          audio: "Pink",
          textoIngles: "The flower is PINK",
        },
        {
          id: 9,
          imagen: "img/colors_blue.jpg",
          color: "white",
          textoEspaniol: "La nube es blanca",
          audio: "White",
          textoIngles: "The cloud is white",
        },
      ],
      color: "",
      imagen: "",
      textoEspaniol: "",
      textoIngles: "",
      audio: "",

      dense: false,
    };
  },

  methods: {
    crearAudio(sound) {
      var number = document.getElementById(sound);
      number.play();
      console.log(sound);
      this.arrayImagesColors.map((item) => {
        if (item.audio.toLowerCase() === sound.toLowerCase()) {
          console.log(item);
          this.color = item.color;
          this.imagen = item.imagen;
          this.textoIngles = item.textoIngles;
          this.textoEspaniol = item.textoEspaniol;
          this.audio = item.audio;
        }
      });
    },
  },
};

//etiquetaAudio.play();
</script>

<style lang="sass" scoped>
.color-card:hover
  transform: scale(1.1)
  transition: .2s
  z-index: 1000

div.row>div:hover
  transform: scale(1.1)
  transition: .2s
  z-index: 1000

.q-btn
  width: 30%
  height: 70px
  margin-bottom: 0.5rem
  padding-top: 0.3rem

.q-btn_mitad
  width: 45%
  height: 70px
  margin-bottom: 0.5rem
  padding-top: 0.3rem

h6
  margin-top: -0.5rem

.qScrollStyle
  height: 100%
  width: 100%
</style>
