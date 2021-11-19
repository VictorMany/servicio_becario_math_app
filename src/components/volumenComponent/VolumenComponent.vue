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
        min-width: 230px;
        padding: 0.4rem;
        border-radius: 0.5rem;
        align: center;
        font-weight: bold;
      "
      class="bg-indigo-13 text-white text-center"
    >
      Volumenes
    </h4>

    <div class="row q-col-gutter-xs">
      <div class="col-12" v-for="n in 6" :key="`xs-${n}`">
        <q-btn
          color="blue-13"
          style="width: 100%; height: 100%"
          align="between"
        >
          <div class="row" style="width: 100%; height: 100%">
            <div class="col-4 bg-white" style="height: 100%">
              <q-img :src="images[n - 1]" style="width: 100%; height: 100%" />
            </div>

            <div class="col" style="width: 100%; border-radius: 0.5rem">
              <q-item>
                <q-item-section>
                  <q-item-label class="bg-indigo" style="padding: 1rem"
                    ><strong>{{ info[n - 1].name }}</strong></q-item-label
                  >
                  <br />
                  <q-item-label caption class="text-left text-capitalize">
                    <strong>Volumen: </strong>
                    {{ info[n - 1].area }}
                  </q-item-label>
                  <q-item-label caption class="text-left text-capitalize">
                    <strong>Fórmula: </strong> {{ info[n - 1].formula }}
                  </q-item-label>
                </q-item-section>
              </q-item>
            </div>
          </div>
        </q-btn>
      </div>
    </div>

    <audio id="correct"><source src="sounds/bien.mp3" /></audio>
  </div>
</template>

<script>
import { useQuasar } from "quasar";

export default {
  name: "GeomtriaComponent",
  data() {
    return {
      images: [
        "img/img-fig3d/cilindro.png",
        "img/img-fig3d/cubo.png",
        "img/img-fig3d/esfera.png",
        "img/img-fig3d/piramide-cuadrangular.png",
        "img/img-fig3d/pirmaide-circular.png",
        "img/img-fig3d/prisma-rectangular.png",
      ],
      info: [
        {
          name: "Cilindro",
          area: "Pi por radio al cuadrado por la altura",
          formula: "V = (π*r²)*h",
        },
        {
          name: "Cubo",
          area: "Lado por lado por lado",
          formula: "V = l*l*l",
        },
        {
          name: "Esfera",
          area: "Cuatro tercios multiplicados por pi por radio al cubo",
          formula: "V = 4/3π*r^3",
        },
        {
          name: "Piramide cuadrangular",
          area: "Lado al cuadrado por altura entre 3",
          formula: "V = (l² * h)/3",
        },

        {
          name: "Piramide circular",
          area: "(Un tercio de pi) por radio al cuadrado por la altura",
          formula: "V = (l² * h)/3",
        },
        {
          name: "Prisma rectangular",
          area: "Lado alto por lado ancho por lado largo",
          formula: "V = a*b*c",
        },
      ],
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

.my-content:hover
  transform: scale(1.05)
</style>
