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
      Divisiones
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
              src="https://www.youtube.com/embed/iA0fP4tL67s"
            />

          </div>
        </q-expansion-item>

        <q-expansion-item
          expand-separator
          icon="scatter_plot"
          label="Infografía"
        >
          <q-img class="img" src="img/img-divisiones/info2.jpeg"></q-img>
          <q-img class="img" src="img/img-divisiones/info.jpeg"></q-img>
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
