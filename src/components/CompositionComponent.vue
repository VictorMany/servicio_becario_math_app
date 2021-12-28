<template>
  <div
    class="bg-light-blue-1 column items-center"
    style="
      width: 100%;
      height: 100%;
      padding-right: 2rem;
      padding-left: 2rem;
      padding-top: 1rem;
    "
  >
    <div class="row" style="max-width: 500px; height; 100%;">
      <div class="col-6" style="padding: 0.5rem">
        <!--Sumas-->
        <div class="div-menu inset-shadow-down bg-blue-2" @click="sumas = true">
          <div class="column items-center">
            <q-img
              basic
              src="img/main_cards/suma.png"
              style="width: 80%; height: 80%; margin-top: 1rem"
            />
          </div>
        </div>
        <!--Restas-->
        <div
          class="div-menu inset-shadow-down bg-blue-6"
          @click="restas = true"
        >
          <div class="column items-center">
            <q-img
              basic
              src="img/main_cards/menos.png"
              style="width: 80%; height: 80%; margin-top: 1rem"
            />
          </div>
        </div>
        <!--Multiplicaciones-->
        <div
          class="div-menu inset-shadow-down bg-light-blue"
          @click="multiplicaciones = true"
        >
          <div class="column items-center" style="overflow: scroll">
            <q-img
              basic
              src="img/main_cards/multiplicacion.png"
              style="width: 80%; height: 80%"
            />
          </div>
        </div>
        <!--Divisiones-->
        <div
          class="div-menu inset-shadow-down bg-cyan-13"
          @click="divisiones = true"
        >
          <div class="column items-center">
            <q-img
              basic
              src="img/main_cards/division.png"
              style="width: 80%; height: 80%"
            />
          </div>
        </div>
        <!--Geometria-->
        <div
          class="div-menu_dos inset-shadow-down bg-blue-14"
          @click="geometria = true"
        >
          <div class="column items-center">
            <h6>Figuras</h6>
            <p>Geométricas</p>
          </div>
        </div>
      </div>
      <div class="col-6" style="padding: 0.5rem">
        <!--Sumas-->
        <div
          class="div-menu_dos inset-shadow-down bg-cyan-13"
          @click="p_sumas = true"
        >
          <div class="column items-center">
            <h6>Practicar</h6>
            <p>Sumas</p>
          </div>
        </div>
        <!--Restas-->
        <div
          class="div-menu_dos inset-shadow-down bg-light-blue"
          @click="p_restas = true"
        >
          <div class="column items-center">
            <h6>Practicar</h6>
            <p>Restas</p>
          </div>
        </div>
        <!--Multiplicaciones-->
        <div
          class="div-menu_dos inset-shadow-down bg-blue-6"
          @click="p_multiplicaciones = true"
        >
          <div class="column items-center">
            <h6>Practicar</h6>
            <p>Multiplicaciones</p>
          </div>
        </div>
        <!--Divisiones-->
        <div
          class="div-menu_dos inset-shadow-down bg-blue-14"
          @click="p_divisiones = true"
        >
          <div class="column items-center">
            <h6>Practicar</h6>
            <p>Divisiones</p>
          </div>
        </div>
        <!--Volumen-->
        <div
          class="div-menu_dos inset-shadow-down bg-blue-14"
          @click="volumen = true"
        >
          <div class="column items-center">
            <h6>Aprender</h6>
            <p>Volumenes</p>
          </div>
        </div>
      </div>
      <!--Preguntas aleatorias-->
      <div style="padding-left: 0.5rem; padding-right: 0.5rem; width: 100%">
        <div
          class="div-menu_dos inset-shadow-down bg-green-14"
          @click="preguntas = true"
        >
          <div class="column items-center">
            <h6>Preguntas</h6>
            <p>aleatorias</p>
          </div>
        </div>
      </div>
    </div>

    <!--Aprender a sumar-->
    <q-dialog v-model="sumas" transition-show="rotate" transition-hide="rotate">
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section>
          <sumas-component></sumas-component>
        </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-blue-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <!--practicar sumas-->
    <q-dialog
      v-model="p_sumas"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section>
          <sumas-component-questions />
        </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-red-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <!--Aprender a restas-->
    <q-dialog
      v-model="restas"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section>
          <restas-component />
        </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-blue-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <!--practicar restas-->
    <q-dialog
      v-model="p_restas"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section>
          <restas-component-questions />
        </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-red-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <!--Aprender a multiplicar-->
    <q-dialog
      v-model="multiplicaciones"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section>
          <multiplicaciones-component />
        </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-blue-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <!--practicar multiplicaciones-->
    <q-dialog
      v-model="p_multiplicaciones"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section>
          <multiplicaciones-component-questions />
        </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-red-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <!--Aprender a dividir-->
    <q-dialog
      v-model="divisiones"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section> <divisiones-component /> </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-blue-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <!--practicar divisiones-->
    <q-dialog
      v-model="p_divisiones"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section>
          <divisiones-component-questions />
        </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-red-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <!--Aprender geometria-->
    <q-dialog
      v-model="geometria"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section>
          <geometria-component></geometria-component>
        </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-red-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <!--Aprender volumenes-->
    <q-dialog
      v-model="volumen"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section>
          <volumen-component></volumen-component>
        </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-red-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>

    <!--Practicar preguntas aleatorias-->
    <q-dialog
      v-model="preguntas"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <q-card style="background-color: #25252500; overflow: scroll">
        <q-card-section>
          <Preguntas />
        </q-card-section>

        <q-separator />
        <q-card-actions align="center" class="bg-red-13">
          <q-btn
            flat
            text-color="white"
            style="width: 100%; height: 100%"
            outline
            label="Cerrar"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </div>
</template>

<script lang="ts">
import SumasComponentQuestions from "./sumasComponent/SumasComponentQuestions.vue";
import RestasComponentQuestions from "./restasComponent/RestasComponentQuestions.vue";
import MultiplicacionesComponentQuestions from "./multiplicacionesComponent/MultiplicacionesComponentQuestions.vue";
import SumasComponent from "./sumasComponent/SumasComponent.vue";
import GeometriaComponent from "./geometriaComponents/GeometriaComponent.vue";
import VolumenComponent from "./volumenComponent/VolumenComponent.vue";
import RestasComponent from "./restasComponent/RestasComponent.vue";
import DivisionesComponent from "./divisionesComponent/DivisionesComponent.vue";
import MultiplicacionesComponent from "./multiplicacionesComponent/MultiplicacionesComponent.vue";
import DivisionesComponentQuestions from "./divisionesComponent/DivisionesComponentQuestions.vue";
import Preguntas from "./preguntasAleatorias/PreguntasComponent.vue";

export default {
  components: {
    SumasComponentQuestions,
    RestasComponentQuestions,
    MultiplicacionesComponentQuestions,
    SumasComponent,
    RestasComponent,
    MultiplicacionesComponent,
    DivisionesComponent,
    DivisionesComponentQuestions,
    GeometriaComponent,
    VolumenComponent,
    Preguntas,
  },
  name: "CompositionComponent",
  props: {
    title: {
      type: String,
      required: true,
    },

    active: {
      type: Boolean,
    },
  },
  data() {
    return {
      sumas: false,
      preguntas: false,
      divisiones: false,
      restas: false,
      multiplicaciones: false,
      geometria: false,
      volumen: false,
      p_multiplicaciones: false,
      p_divisiones: false,
      p_restas: false,
      p_sumas: false,
      thumbStyle: {
        right: "-6px",
        borderRadius: "1px",
        backgroundColor: "#027be3",
        width: "2px",
        opacity: 0.75,
      },
      barStyle: {
        right: "-6px",
        borderRadius: "9px",
        backgroundColor: "#027be3",
        width: "2px",
        opacity: 0.2,
      },
    };
  },

  methods: {},
};
</script>

<style scoped lang="sass">
.div-menu
  width: 100%
  height: 140px
  color: white
  padding: 1rem
  margin-bottom: 1rem
  border-radius: 1rem

.div-menu_dos
  width: 100%
  height: 140px
  color: white
  padding: 1rem
  padding-top: 3rem
  margin-bottom: 1rem
  border-radius: 1rem

p
  margin-top: -3rem
  color: light-grey
  font-weight: bold

h6
  margin-top: -0.3rem
  font-size: 20fpx

.qScrollStyle
  height: calc(100%)
  width: 100%

div
  overflow: hidden
</style>
