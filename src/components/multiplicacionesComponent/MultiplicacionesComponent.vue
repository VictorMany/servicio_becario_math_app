<template>
  <div
    class="q-pa-md"
    style="
      width: 100%;
      height: 100%;
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
        min-width: 230px;
      "
      class="bg-blue-13 text-white text-center"
    >
      Multiplicaciones
    </h4>

    <div>
      <q-list bordered class="rounded-borders">
        <q-expansion-item
          expand-separator
          icon="videocam"
          label="Video introductorio"
        >
          <div class="img">
            <q-video
              :ratio="16 / 9"
              src="https://www.youtube.com/embed/YFtEaVw5k1A"
            />

            <!--https://www.youtube.com/embed/YFtEaVw5k1A-->
            <!--https://www.youtube.com/embed/iA0fP4tL67s-->
          </div>
        </q-expansion-item>

        <q-expansion-item
          expand-separator
          icon="image"
          label="Tablas de multiplicar"
        >
          <q-card>
            <q-card-section>
              <q-img class="img" src="img/img-sumas/t1.jpeg"></q-img>
            </q-card-section>
          </q-card>
          <q-card>
            <q-card-section>
              <q-img class="img" src="img/img-sumas/t2.jpeg"></q-img>
            </q-card-section>
          </q-card>
          <q-card>
            <q-card-section>
              <q-img class="img" src="img/img-sumas/t3.jpeg"></q-img>
            </q-card-section>
          </q-card>
          <q-card>
            <q-card-section>
              <q-img class="img" src="img/img-sumas/t4.jpeg"></q-img>
            </q-card-section>
          </q-card>
          <q-card>
            <q-card-section>
              <q-img class="img" src="img/img-sumas/t5.jpeg"></q-img>
            </q-card-section>
          </q-card>
          <q-card>
            <q-card-section>
              <q-img class="img" src="img/img-sumas/t6.jpeg"></q-img>
            </q-card-section>
          </q-card>
          <q-card>
            <q-card-section>
              <q-img class="img" src="img/img-sumas/t7.jpeg"></q-img>
            </q-card-section>
          </q-card>
          <q-card>
            <q-card-section>
              <q-img class="img" src="img/img-sumas/t8.jpeg"></q-img>
            </q-card-section>
          </q-card>
          <q-card>
            <q-card-section>
              <q-img class="img" src="img/img-sumas/t9.jpeg"></q-img>
            </q-card-section>
          </q-card>
          
        </q-expansion-item>

        <q-expansion-item
          expand-separator
          icon="scatter_plot"
          label="Infografía"
        >
          <q-img class="img" src="img/img-sumas/info2.png"></q-img>
          <q-img class="img" src="img/img-sumas/info.jpeg"></q-img>
        </q-expansion-item>
      </q-list>
    </div>
  </div>
</template>

<script>
export default {};

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
</style>
