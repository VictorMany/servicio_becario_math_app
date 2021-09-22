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
        font-weight: bold;
      "
      class="bg-indigo-13 text-white text-center"
    >
      Sumas
    </h4>

    <q-list bordered class="rounded-borders">
      <q-expansion-item
        expand-separator
        icon="looks_one"
        label="Sumas con una cifra"
      >
        <div class="row q-col-gutter-xs">
          <div class="col-4" v-for="n in 18" :key="`xs-${n}`">
            <q-btn
              :color="color[n - 1]"
              style="width: 100%"
              :outline="colors[n - 1]"
              @click="hacerPares(n, '1c')"
              align="between"
              class="my-content"
            >
              <div class="items-center" style="width: 100%">
                {{ numbersArray[n - 1] }}
              </div>
            </q-btn>
          </div>
        </div>
      </q-expansion-item>

      <q-expansion-item
        expand-separator
        icon="looks_two"
        label="Sumas con dos cifras"
      >
        <div class="row q-col-gutter-xs">
          <div class="col-4" v-for="n in 18" :key="`xs-${n}`">
            <q-btn
              :color="color[n - 1]"
              style="width: 100%"
              :outline="colors[n - 1]"
              @click="hacerPares(n, '2c')"
              align="between"
              class="my-content"
            >
              <div class="items-center" style="width: 100%">
                {{ numbersArray[n - 1] }}
              </div>
            </q-btn>
          </div>
        </div>
      </q-expansion-item>

      <q-expansion-item
        expand-separator
        icon="looks_3"
        label="Sumas con tres cifras"
      >
        <div class="row q-col-gutter-xs">
          <div class="col-4" v-for="n in 18" :key="`xs-${n}`">
            <q-btn
              :color="color[n - 1]"
              style="width: 100%"
              :outline="colors[n - 1]"
              @click="hacerPares(n, '3c')"
              align="between"
              class="my-content"
            >
              <div class="items-center" style="width: 100%">
                {{ numbersArray[n - 1] }}
              </div>
            </q-btn>
          </div>
        </div>
      </q-expansion-item>
    </q-list>
  </div>
</template>

<script>
import CardImgSuma from "./CardImgSuma.vue";
import { useQuasar } from "quasar";

export default {
  components: { CardImgSuma },

  created() {
    this.functions();
  },

  setup() {
    const $q = useQuasar();

    return {
      showNotif() {
        $q.notify({
          message: "Felicidades, muy bien hecho !!",
          color: "green",
          position: "center",
          multiLine: true,
          icon: "check",
        });
      },
    };
  },

  methods: {
    functions() {
      for (let i = 0; i <= 17; i++) {
        if (i < 9) {
          let suma =
            this.found(i).toString() + " + " + this.found(i + 1).toString();
          this.numbersArray.push(suma);
        } else this.numbersArray.push(this.foundResult(i));
      }

      //console.log(this.numbersArray);
    },

    found(n) {
      let number = Math.floor(Math.random() * (100 - 0) + 1);
      return number;
    },

    foundResult(n) {
      let result = eval(this.numbersArray[n - 9]);
      for (let i = 0; i < 9; i++) {
        this.aleatorio();
      }
      // console.log(this.numbersAleatorios);
      //console.log(n, this.numbersAleatorios[n - 9]);
      this.numbersArray[this.numbersAleatorios[n - 9]] = result;
    },

    hacerPares(a, cifra) {
      if (this.colors[a - 1]) {
        this.cont++;
        let val1, val2;

        if (a <= 9) {
          val1 = eval(this.numbersArray[a - 1]);
          console.log(val1);
          this.matches.push({
            val: val1,
            a: a,
            string: this.numbersArray[a - 1],
          });
          this.color[this.matches[0].a - 1] = "orange-13";
          this.colors[this.matches[0].a - 1] = false;
        } else {
          val2 = eval(this.numbersArray[a - 1]);
          this.matches.push({
            val: val2,
            a: a,
            string: this.numbersArray[a - 1],
          });
          this.color[this.matches[0].a - 1] = "orange-13";
          this.colors[this.matches[0].a - 1] = false;
        }

        if (
          this.matches.length == 2 &&
          this.matches[0] &&
          this.matches[1] &&
          this.matches[0].val == this.matches[1].val &&
          this.matches[0].string != this.matches[1].string
        ) {
          console.log(this.matches[0].val, this.matches[1].val);
          this.color[this.matches[0].a - 1] = "blue-13";
          this.color[this.matches[1].a - 1] = "blue-13";
          this.colors[this.matches[0].a - 1] = false;
          this.colors[this.matches[1].a - 1] = false;
          this.matches = [];

          if (!this.colors.includes(true)) {
            console.log("yaaaaaa");
            this.showNotif();
          }
        } else if (this.matches.length == 2) {
          console.log(this.matches[0].val, this.matches[1].val);
          console.log("Unmatch");
          this.color[this.matches[0].a - 1] = "blue-13";
          this.color[this.matches[1].a - 1] = "blue-13";
          this.colors[this.matches[0].a - 1] = true;
          this.colors[this.matches[1].a - 1] = true;

          this.matches = [];
        }
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
      numbersArray: [],
      numbersArrayResults: [],
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
      color: [
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
        "blue-13",
      ],

      matches: [],
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
  height: 60px
  border: 1px solid rgba(86,61,124,.2)
</style>
