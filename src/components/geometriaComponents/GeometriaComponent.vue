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
      Figuras geométricas
    </h4>

    <div class="row q-col-gutter-xs">
      <div class="col-12" v-for="n in 10" :key="`xs-${n}`">
        <q-btn
          color="blue-13"
          style="width: 100%; height: 100%"
          align="between"
        >
          <div class="row" style="width: 100%; height: 100%">
            <div class="col-4 bg-white" style="height: 100%">
              <q-img :src="images[n - 1]" style="width: 100%" />
            </div>

            <div class="col" style="width: 100%; border-radius: 0.5rem">
              <q-item>
                <q-item-section>
                  <q-item-label class="bg-indigo" style="padding: 1rem"
                    ><strong>{{ info[n - 1].name }}</strong></q-item-label
                  >
                  <br />
                  <q-item-label
                    no-caps
                    caption
                    class="text-left text-capitalize"
                  >
                    <strong>Área: </strong>
                    {{ info[n - 1].area }}
                  </q-item-label>
                  <q-item-label
                    no-caps
                    caption
                    class="text-left text-capitalize"
                  >
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
        "img/img-figuras/circulo.png",
        "img/img-figuras/triangulo.png",
        "img/img-figuras/cuadrado.png",
        "img/img-figuras/rectangulo.png",
        "img/img-figuras/rombo.png",
        "img/img-figuras/romboide.png",
        "img/img-figuras/trapecio.png",
        "img/img-figuras/pentagono.png",
        "img/img-figuras/hexagono.png",
        "img/img-figuras/octagono.png",
      ],
      info: [
        {
          name: "Circulo",
          area: "Pi por radio al cuadrado",
          formula: "A = π*r²",
        },
        {
          name: "Triángulo",
          area: "Base por altura entre dos",
          formula: "A = b*h/2",
        },
        {
          name: "Cuadrado",
          area: "Base por altura",
          formula: "A = b*h",
        },
        {
          name: "Rectángulo",
          area: "Base por altura",
          formula: "A = b*h",
        },

        {
          name: "Rombo",
          area: "(Diagonal mayor por diagonal menor) entre dos",
          formula: "A = (D*d)/2",
        },
        {
          name: "Romboide",
          area: "Base por altura",
          formula: "A = b*h",
        },
        {
          name: "Trapecio",
          area: "((Base uno más base dos) por altura )divido sobre dos",
          formula: "A = ((B+b)*h)/2",
        },
        {
          name: "Pentágono",
          area: "Cinco veces un lado por apotema divido entre 2",
          formula: "A = (5*L*a)/2",
        },
        {
          name: "Hexágono",
          area: "Seis veces un lado por apotema divido entre 2",
          formula: "A = (6*L*a)/2",
        },
        {
          name: "Octágono",
          area: "Ocho veces un lado por apotema divido entre 2",
          formula: "A = (8*L*a)/2",
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
