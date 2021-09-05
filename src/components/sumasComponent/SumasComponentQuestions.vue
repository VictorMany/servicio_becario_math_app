<template>
  <div
    class="q-pa-md"
    style="width: 100%; height: 90%; background-color: rgb(10, 10, 10, 0.8)"
  >
    <h4
      style="
        margin-top: -0.3rem;
        margin-bottom: 2rem;
        width: 100%;
        padding: 0.4rem;
        border-radius: 0.5rem;
        text-align: center;
        font-weight: bold;
      "
      class="bg-blue-13 text-white"
    >
      Colors
    </h4>
    <div class="row justify-around" style="margin-bottom: 1rem">
      <audio id="red"><source src="colors/red.mp3" /></audio>
      <audio id="blue"><source src="colors/blue.mp3" /></audio>
      <audio id="yellow"><source src="colors/yellow.mp3" /></audio>
      <audio id="green"><source src="colors/green.mp3" /></audio>
      <audio id="orange"><source src="colors/orange.mp3" /></audio>
      <audio id="purple"><source src="colors/purple.mp3" /></audio>
      <audio id="grey"><source src="colors/grey.mp3" /></audio>
      <audio id="pink"><source src="colors/pink.mp3" /></audio>
      <audio id="white"><source src="colors/white.mp3" /></audio>
      <audio id="correct"><source src="numbers/sounds/correct.mp3" /></audio>
      <audio id="incorrect">
        <source src="numbers/sounds/incorrect.mp3" />
      </audio>

      <q-btn
        style="width: 100%; height: auto"
        push
        class="q-btn"
        @click="cargarAudiosColorsAleatorio"
        color="light-blue-13"
        icon="campaign"
      >
        <div class="row justify-center" style="width: 100%">CLICK ME !!</div>
        <p class="row justify-center text-white" style="font-size: 0.6rem">
          Presióname
        </p>
      </q-btn>
    </div>

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
          @click="comprobar('blue')"
        />
        <div
          class="col bg-white"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="comprobar('white')"
        />
        <div
          class="col bg-red-13"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="comprobar('red')"
        />
      </div>
      <div class="row">
        <div
          class="col bg-purple"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="comprobar('purple')"
        />
        <div
          class="col bg-green-14"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="comprobar('green')"
        />
        <div
          class="col bg-orange-10"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="comprobar('orange')"
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
          @click="comprobar('yellow')"
        />
        <div
          class="col bg-pink"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="comprobar('pink')"
        />
        <div
          class="col bg-grey-7"
          style="
            width: 90%;
            height: 80px;
            border-radius: 0.5rem;
            margin: 0.5rem;
          "
          @click="comprobar('grey')"
        />
      </div>
    </div>

    <div class="row" style="margin-top: 1rem">
      <q-btn
        style="width: 100%; border-radius: 0.5rem"
        icon="repeat"
        class="bg-blue text-white"
        label="Repeat"
        @click="repeat"
      >
      </q-btn>
    </div>

    <div style="margin-top: 2rem; margin-bottom: 1rem">
      <div class="row justify-around text-white">
        <div
          class="bg-green-14 col text-center"
          style="
            padding: 0.5rem;
            border-radius: 0.5rem;
            font-weight: bold;
            margin: 0 0.5rem 0 0.5rem;
          "
        >
          <p
            style="
              background-color: rgb(0, 0, 0, 0.3);
              padding: 0.5rem;
              border-radius: 0.5rem;
            "
          >
            Good
          </p>

          <p
            class="text-grey-4 text-justify"
            style="
              background-color: rgb(0, 0, 0, 0.3);
              padding: 0.5rem;
              border-radius: 0.5rem;
            "
          >
            Si obtienes un verde es que vas muy bien :)
          </p>
        </div>
        <div
          class="bg-red-13 col text-center"
          style="
            padding: 0.5rem;
            border-radius: 0.5rem;
            font-weight: bold;
            margin: 0 0.5rem 0 0.5rem;
          "
        >
          <p
            style="
              background-color: rgb(0, 0, 0, 0.3);
              padding: 0.5rem;
              border-radius: 0.5rem;
            "
          >
            Wrong
          </p>
          <p
            class="text-grey-4 text-justify"
            style="
              background-color: rgb(0, 0, 0, 0.3);
              padding: 0.5rem;
              border-radius: 0.5rem;
            "
          >
            Si obtienes un rojo es que deberías de estudiar más los colores
          </p>
        </div>
      </div>
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
export default {
  data() {
    return {
      numbers_0_20: false,
      numbers_tens: false,
      numbers_hundreds: false,
      numbers_thousands: false,
      text: "",
      ph: "",

      dense: false,

      arregloColors: [
        { number: 0, ruta: "red" },
        { number: 1, ruta: "blue" },
        { number: 2, ruta: "yellow" },
        { number: 3, ruta: "green" },
        { number: 4, ruta: "orange" },
        { number: 5, ruta: "purple" },
        { number: 6, ruta: "grey" },
        { number: 7, ruta: "pink" },
        { number: 8, ruta: "white" },
      ],

      currentObject: {},
    };
  },

  methods: {
    crearAudio(sound) {
      console.log(sound.ruta, sound.number);
      var number = document.getElementById(sound.ruta);
      number.play();
    },

    cargarAudiosColorsAleatorio() {
      let number = Math.floor(Math.random() * (9 - 0) + 0);
      this.arregloColors.map((x) => {
        if (x.number == number) {
          this.crearAudio(x);
          this.currentObject = { ...x };
        }
      });
    },

    async comprobar(text) {
      try {
        console.log("Hoola");
        console.log("Numero del input", text);
        console.log("Numero dicho de voz", this.currentObject.number);

        if (text === this.currentObject.ruta.toString()) {
          var number = document.getElementById("correct");
          await number.play();
          this.$q.notify({
            type: "positive",
            message: `Vas muy bien !!`,
          });

          text = "";
        } else {
          var number = document.getElementById("incorrect");
          await number.play();

          this.$q.notify({
            type: "negative",
            message: `Try Again!!`,
          });
        }
      } catch (error) {}
    },

    repeat() {
      try {
        this.crearAudio(this.currentObject);
      } catch (error) {}
    },
  },
};

//etiquetaAudio.play();
</script>

<style lang="sass" scoped>
.button
  color: $blue
  padding: 0.3rem
  margin: 0.2rem

.q-btn
  width: 30%
  height: 70px
  margin-bottom: 0.5rem
  padding-top: 0.3rem

div.row>div:hover
  transform: scale(1.1)
  transition: .2s
  z-index: 1000

h6
  margin-top: -0.5rem

.qScrollStyle
  height: 100%
  width: 100%
</style>
