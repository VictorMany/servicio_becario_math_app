<template>
  <div
    class="q-pa-md"
    style="
      width: 100%;
      height: 100%;
      background-color: rgb(10, 10, 10, 0.95);
      overflow: scroll;
    "
  >
    <h4
      style="
        margin-top: -0.3rem;
        margin-bottom: 1.5rem;
        width: 100%;
        padding: 0.4rem;
        border-radius: 0.5rem;
        align: center;
        min-width: 230px;
        font-weight: bold;
      "
      class="bg-indigo-13 text-white text-center"
    >
      Preguntas aleatorias
    </h4>

    <q-btn
      style="width: 100%; height: 70px; margin-bottom: 1.5rem"
      push
      class="q-btn"
      @click="functions()"
      color="light-blue-13"
      icon="help"
    >
      <div class="row justify-center" style="width: 100%">
        GENERA OPERACIÓN !!
      </div>
    </q-btn>

    <div class="row q-col-gutter-xs">
      <div class="col-12" v-for="n in 1" :key="`xs-${n}`">
        <q-btn
          color="blue-3"
          
          style="width: 100%"
          align="between"
          class="my-content"
        >
          <div class="row" style="width: 100%; height: 70%">
            <div class="col" style="overflow: hidden">
              <img :src="image" style="height: 80px" />
            </div>
          </div>
          <div
            :class="['row', 'bg-orange-14']"
            style="
              width: 100%;
              height: 30%;
              border-radius: 0.5rem;
              margin-top: -0.9rem;
            "
          >
            <div
              class="items-center row justify-center text-capitalize"
              style="
                width: 100%;
                font-size: 20px;
                overflow: scroll;
                padding-top: 0.3rem;
              "
            >
              ¿CUANTO ES {{ numbersArray[n - 1] }} ?
            </div>
          </div>
        </q-btn>
      </div>
    </div>

    <q-input
      class="bg-blue-3 text-white"
      bottom-slots
      type="number"
      v-model="text"
      label="Escribe la respuesta de la operación"
      :dense="dense"
      style="
        padding: 0.5rem;
        height: auto;
        border-radius: 1rem;
        color: white;
        margin-top: 1rem;
      "
    >
      <template v-slot:append>
        <q-icon
          v-if="text !== ''"
          name="close"
          @click="text = ''"
          class="cursor-pointer text-white"
        />
      </template>

      <template v-slot:after>
        <q-btn
          style="width: 100%; height: 40px; padding: 0.2rem"
          round
          dense
          color="green-10 bg-green-13"
          push
          icon="send"
          @click="comprobar"
        />
      </template>
    </q-input>
    <audio id="correct"><source src="sounds/bien.mp3" /></audio>
    <audio id="incorrect">
      <source src="sounds/mal.mp3" />
    </audio>
    <audio id="beep">
      <source src="sounds/beep.mp3" />
    </audio>
  </div>
</template>

<script>
import { useQuasar } from "quasar";

export default {
  created() {
    this.functions();
  },

  setup() {
    const $q = useQuasar();

    return {
      showNotif() {
        beep.play();
        $q.notify({
          message: "¡Muy bien hecho!",
          color: "blue-10",
          multiLine: true,
          icon: "check",
        });
      },
      mal() {
        incorrect.play();
        $q.notify({
          message: "¡Intenta de nuevo!",
          color: "red-10",
          multiLine: true,
          icon: "dangerous",
        });
      },
    };
  },

  methods: {
    functions() {
      this.cleanArrays();

      this.image = this.images[this.aleatorio(0, 17)];

      let operacion =
        this.found(1, 20).toString() +
        this.operaciones[this.aleatorio(0, 3)] +
        this.found(1, 9).toString();
      this.numbersArray.push(operacion);

      console.log(this.numbersArray);
    },

    cleanArrays() {
      this.auxArray = [];
      this.numbersArray = [];
    },

    repetido(num) {
      return this.numbersAleatorios.includes(num);
    },

    found(min, max) {
      //console.log(min, max);
      let number = Math.floor(Math.random() * (max - min + 1) + min);
      return number;
    },

    foundResult(n) {
      let result = eval(this.numbersArray[n - 9]);
      for (let i = 0; i < 9; i++) {
        this.aleatorio();
      }
      this.numbersArray[this.numbersAleatorios[n - 9]] = result;
    },

    aleatorio(min = 9, max = 18) {
      if (this.numbersAleatorios.length != max - min) {
        while (repe != false) {
          var num = Math.floor(Math.random() * (18 - 9)) + 9;
          var repe = this.repetido(num);
        }
        this.numbersAleatorios.push(num);
        return num;
      } else {
        return;
      }
    },

    aleatorio(min = 0, max = 17) {
      var num = Math.floor(Math.random() * (max - min)) + min;
      return num;
    },

    comprobar() {
      if (this.text != "") {
        if (Number(eval(this.numbersArray[0])) === Number(this.text)) {
          this.functions();
          this.text = "";
          this.showNotif();
          this.image = this.images[this.aleatorio(0, 17)];
        } else {
          console.log("Mal");
          this.mal();
        }
      }
    },
  },

  data() {
    return {
      numbers_0_20: false,
      numbers_tens: false,
      numbers_hundreds: false,
      numbers_thousands: false,
      text: "",
      image: "img/img-sumas/1.png",
      ph: "",
      dense: false,

      currentObject: {},

      cont: 0,
      auxArray: [],
      numbersArray: [],
      operaciones: ["+", "-", "*"],
      numbersArrayResults: [],

      numbersAleatorios: [],

      images: [
        "img/img-sumas/1.png",
        "img/img-sumas/2.png",
        "img/img-sumas/3.png",
        "img/img-sumas/4.png",
        "img/img-sumas/5.png",
        "img/img-sumas/6.png",
        "img/img-sumas/7.png",
        "img/img-sumas/8.png",
        "img/img-sumas/9.png",
        "img/img-sumas/10.png",
        "img/img-sumas/11.png",
        "img/img-sumas/12.png",
        "img/img-sumas/13.png",
        "img/img-sumas/14.png",
        "img/img-sumas/15.png",
        "img/img-sumas/16.png",
        "img/img-sumas/17.png",
        "img/img-sumas/18.png",
      ],

      matches: [],
      matches2: [],
      matches3: [],
      auxColors: [],
      auxColor: [],
      auxMatches: [],
    };
  },
};

//etiquetaAudio.play();
</script>

<style lang="sass" scoped>
h6
  margin-top: -0.5rem

.qScrollStyle
  height: 100%
  width: 100%

div
  color: white

.my-content
  padding: 10px 15px
  height: 140px
  border: 1px solid rgba(86,61,124,.2)
</style>
