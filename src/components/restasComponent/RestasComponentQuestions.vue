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
        margin-bottom: 2rem;
        width: 100%;
        padding: 0.4rem;
        border-radius: 0.5rem;
        align: center;
        min-width: 230px;
        font-weight: bold;
      "
      class="bg-indigo-13 text-white text-center"
    >
      Restas
    </h4>

    <q-list bordered class="rounded-borders">
      <q-expansion-item
        expand-separator
        icon="looks_one"
        label="Nivel 1"
      >
        <q-btn
          color="orange"
          style="width: 100%; margin-top: 1rem; margin-bottom: 1rem"
          @click="functions()"
          label="Generar nuevas Restas"
        />

        <div class="row q-col-gutter-xs">
          <div class="col-6" v-for="n in 18" :key="`xs-${n}`">
            <q-btn
              :color="color[n - 1]"
              style="width: 100%"
              :outline="colors[n - 1]"
              @click="hacerPares(n, '')"
              align="between"
              class="my-content"
            >
              <div class="row" style="width: 100%; height: 70%">
                <div class="col" style="overflow: hidden">
                  <img :src="images[n - 1]" style="height: 80px" />
                </div>
              </div>
              <div
                :class="[
                  'row',
                  n >= 1 && n <= 9 ? 'bg-deep-orange' : 'bg-indigo-10',
                ]"
                style="width: 100%; height: 30%; border-radius: 0.5rem;
                  margin-top: -0.9rem"
              >
                <div
                  v-show="n >= 1 && n <= 9"
                  class="items-center row justify-center text-capitalize"
                  style="width: 100%; font-size: 10px; overflow: scroll;
                    padding-top: 0.3rem;"
                >
                  ¿Quién tiene {{ numbersArray[n - 1] }} ?
                </div>
                <div
                  v-show="n > 9"
                  class="items-center row justify-center text-capitalize"
                  style="width: 100%; font-size: 10px; overflow: scroll;
                    padding-top: 0.3rem;"
                >
                  Yo tengo {{ numbersArray[n - 1] }}
                </div>
              </div>
            </q-btn>
          </div>
        </div>
      </q-expansion-item>

      <q-expansion-item
        expand-separator
        icon="looks_two"
        label="Nivel 2"
      >
        <q-btn
          color="orange"
          style="width: 100%; margin-top: 1rem; margin-bottom: 1rem"
          @click="functions()"
          label="Generar nuevas Restas"
        />
        <div class="row q-col-gutter-xs">
          <div class="col-6" v-for="n in 18" :key="`xs-${n}`">
            <q-btn
              :color="color2[n - 1]"
              style="width: 100%"
              :outline="colors2[n - 1]"
              @click="hacerPares(n, '2c')"
              align="between"
              class="my-content"
            >
              <div class="row" style="width: 100%; height: 70%">
                <div class="col" style="overflow: hidden">
                  <img :src="images[n - 1]" style="height: 80px" />
                </div>
              </div>
              <div
                :class="[
                  'row',
                  n >= 1 && n <= 9 ? 'bg-deep-orange' : 'bg-indigo-10',
                ]"
                style="width: 100%; height: 30%; border-radius: 0.5rem;
                  margin-top: -0.9rem"
              >
                <div
                  v-show="n >= 1 && n <= 9"
                  class="items-center row justify-center text-capitalize"
                  style="width: 100%; font-size: 10px; overflow: scroll;
                    padding-top: 0.3rem;"
                >
                  ¿Quién tiene {{ numbersArray2c[n - 1] }} ?
                </div>
                <div
                  v-show="n > 9"
                  class="items-center row justify-center text-capitalize"
                  style="width: 100%; font-size: 10px; overflow: scroll;
                    padding-top: 0.3rem;"
                >
                  Yo tengo {{ numbersArray2c[n - 1] }}
                </div>
              </div>
            </q-btn>
          </div>
        </div>
      </q-expansion-item>

      <q-expansion-item
        expand-separator
        icon="looks_3"
        label="Nivel 3"
      >
        <q-btn
          color="orange"
          style="width: 100%; margin-top: 1rem; margin-bottom: 1rem"
          @click="functions()"
          label="Generar nuevas Restas"
        />

        <div class="row q-col-gutter-xs">
          <div class="col-6" v-for="n in 18" :key="`xs-${n}`">
            <q-btn
              :color="color3[n - 1]"
              style="width: 100%"
              :outline="colors3[n - 1]"
              @click="hacerPares(n, '3c')"
              align="between"
              class="my-content"
            >
              <div class="row" style="width: 100%; height: 70%">
                <div class="col" style="overflow: hidden">
                  <img :src="images[n - 1]" style="height: 80px" />
                </div>
              </div>
              <div
                :class="[
                  'row',
                  n >= 1 && n <= 9 ? 'bg-deep-orange' : 'bg-indigo-10',
                ]"
                style="width: 100%; height: 30%; border-radius: 0.5rem;
                  margin-top: -0.9rem"
              >
                <div
                  v-show="n >= 1 && n <= 9"
                  class="items-center row justify-center text-capitalize"
                  style="width: 100%; font-size: 10px; overflow: scroll;
                    padding-top: 0.3rem;"
                >
                  ¿Quién tiene {{ numbersArray3c[n - 1] }} ?
                </div>
                <div
                  v-show="n > 9"
                  class="items-center row justify-center text-capitalize"
                  style="width: 100%; font-size: 10px; overflow: scroll;
                    padding-top: 0.3rem;"
                >
                  Yo tengo {{ numbersArray3c[n - 1] }}
                </div>
              </div>
            </q-btn>
          </div>
        </div>
      </q-expansion-item>
    </q-list>
    <audio id="correct"><source src="sounds/bien.mp3" /></audio>
    <audio id="incorrect">
      <source src="sounds/mal.mp3" />
    </audio>
    <audio id="beep">
      <source src="sounds/beep.mp3" />
    </audio>
    <audio id="final">
      <source src="sounds/final.mp3" />
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
        final.play();

        $q.notify({
          message: "Prueba con el siguiente nivel",
          color: "indigo-10",
          position: "center",
          multiLine: true,
        });
        $q.notify({
          message: "Felicidades, muy bien hecho !!",
          color: "indigo-10",
          position: "center",
          multiLine: true,
          icon: "check",
        });
      },
    };
  },

  methods: {
    functions() {
      this.cleanArrays();

      for (let i = 0; i <= 17; i++) {
        if (i < 9) {
          let resta =
            this.found(1, 9).toString() + " - " + this.found(1, 9).toString();
          this.numbersArray.push(resta);
        } else this.numbersArray.push(this.foundResult(i, 1));
      }

      for (let i = 0; i <= 17; i++) {
        if (i < 9) {
          let resta =
            this.found(10, 99).toString() +
            " - " +
            this.found(10, 99).toString();
          this.numbersArray2c.push(resta);
        } else this.numbersArray2c.push(this.foundResult(i, 2));
      }

      for (let i = 0; i <= 17; i++) {
        if (i < 9) {
          let resta =
            this.found(100, 999).toString() +
            " - " +
            this.found(100, 999).toString();
          this.numbersArray3c.push(resta);
        } else this.numbersArray3c.push(this.foundResult(i, 3));
      }
      //console.log(this.numbersArray);
    },

    cleanArrays() {
      this.auxArray = [];
      this.numbersArray = [];
      this.numbersArray2c = [];
      this.numbersArray3c = [];
      this.numbersArrayResults = [];
      this.numbersArrayResults2c = [];
      this.numbersArrayResults3c = [];
      this.numbersAleatorios = [];

      this.colors = [
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
      ];
      (this.colors2 = [
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
      ]),
        (this.colors3 = [
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
          true,
        ]);
      this.color = [
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
      ];
      this.color2 = [
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
      ];
      this.color3 = [
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
      ];
    },

    found(min, max) {
      console.log(min, max);
      let number = Math.floor(Math.random() * (max - min + 1) + min);
      return number;
    },

    foundResult(n, cifra) {
      if (cifra == 1) {
        let result = eval(this.numbersArray[n - 9]);
        for (let i = 0; i < 9; i++) {
          this.aleatorio();
        }
        this.numbersArray[this.numbersAleatorios[n - 9]] = result;
      } else if (cifra == 2) {
        let result = eval(this.numbersArray2c[n - 9]);
        for (let i = 0; i < 9; i++) {
          this.aleatorio();
        }
        this.numbersArray2c[this.numbersAleatorios[n - 9]] = result;
      } else if (cifra == 3) {
        let result = eval(this.numbersArray3c[n - 9]);
        for (let i = 0; i < 9; i++) {
          this.aleatorio();
        }
        this.numbersArray3c[this.numbersAleatorios[n - 9]] = result;
      }
    },

    hacerPares(a, cifra) {
      console.log("Hola como te va", cifra);

      switch (true) {
        case cifra == "":
          this.auxArray = this.numbersArray;
          this.auxColor = this.color;
          this.auxColors = this.colors;
          this.auxMatches = this.matches;
          break;
        case cifra == "2c":
          this.auxArray = this.numbersArray2c;
          this.auxColor = this.color2;
          this.auxColors = this.colors2;
          this.auxMatches = this.matches2;
          break;
        case cifra == "3c":
          this.auxArray = this.numbersArray3c;
          this.auxColor = this.color3;
          this.auxColors = this.colors3;
          this.auxMatches = this.matches3;
          break;
      }

      if (this.auxColors[a - 1]) {
        this.cont++;
        let val1, val2;

        if (a <= 9) {
          val1 = eval(this.auxArray[a - 1]);
          console.log(val1);
          this.auxMatches.push({
            val: val1,
            a: a,
            string: this.auxArray[a - 1].toString(),
          });
          this.auxColor[this.auxMatches[0].a - 1] = "orange-13";
          this.auxColors[this.auxMatches[0].a - 1] = false;
        } else {
          val2 = eval(this.auxArray[a - 1]);
          this.auxMatches.push({
            val: val2,
            a: a,
            string: this.auxArray[a - 1].toString(),
          });
          this.auxColor[this.auxMatches[0].a - 1] = "orange-13";
          this.auxColors[this.auxMatches[0].a - 1] = false;
        }
        console.log(this.auxMatches.length);
        if (this.auxMatches.length == 1) {
          var beep = document.getElementById("beep");
          beep.play();
        }
        if (
          this.auxMatches.length == 2 &&
          this.auxMatches[0] &&
          this.auxMatches[1] &&
          this.auxMatches[0].val == this.auxMatches[1].val &&
          this.auxMatches[0].string != this.auxMatches[1].string &&
          ((this.auxMatches[0].string.includes("-") &&
            !this.auxMatches[1].string[0].includes("-")) ||
            (!this.auxMatches[0].string[0].includes("-") &&
              this.auxMatches[1].string.includes("-")))
        ) {
          console.log(this.auxMatches[0].val, this.auxMatches[1].val);
          this.auxColor[this.auxMatches[0].a - 1] = "green-14";
          this.auxColor[this.auxMatches[1].a - 1] = "green-14";
          this.auxColors[this.auxMatches[0].a - 1] = false;
          this.auxColors[this.auxMatches[1].a - 1] = false;
          this.auxMatches = [];
          var number = document.getElementById("correct");
          number.play();
          if (!this.auxColors.includes(true)) {
            this.showNotif();
          }
        } else if (this.auxMatches.length == 2) {
          console.log(this.auxMatches[0].val, this.auxMatches[1].val);
          console.log("Unmatch");
          var number = document.getElementById("incorrect");
          number.play();
          this.auxColor[this.auxMatches[0].a - 1] = "green-14";
          this.auxColor[this.auxMatches[1].a - 1] = "green-14";
          this.auxColors[this.auxMatches[0].a - 1] = true;
          this.auxColors[this.auxMatches[1].a - 1] = true;

          this.auxMatches = [];
        }
      }

      switch (true) {
        case cifra == "":
          this.numbersArray = this.auxArray;
          this.color = this.auxColor;
          this.colors = this.auxColors;
          this.matches = this.auxMatches;
          break;
        case cifra == "2c":
          this.numbersArray2c = this.auxArray;
          this.color2 = this.auxColor;
          this.colors2 = this.auxColors;
          this.matches2 = this.auxMatches;
          break;
        case cifra == "3c":
          this.numbersArray3c = this.auxArray;
          this.color3 = this.auxColor;
          this.colors3 = this.auxColors;
          this.matches3 = this.auxMatches;
          break;
      }
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

    repetido(num) {
      return this.numbersAleatorios.includes(num);
    },
  },

  data() {
    return {
      cont: 0,
      auxArray: [],
      numbersArray: [],
      numbersArray2c: [],
      numbersArray3c: [],
      numbersArrayResults: [],
      numbersArrayResults2c: [],
      numbersArrayResults3c: [],
      numbersAleatorios: [],
      colors: [
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
      ],
      colors2: [
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
      ],
      colors3: [
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
        true,
      ],
      color: [
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
      ],
      color2: [
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
      ],
      color3: [
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
        "green-14",
      ],

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

.my-content:hover
  transform: scale(1.05)
</style>
