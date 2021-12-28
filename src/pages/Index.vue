<template>
   <q-page style="background-color: #969EA1;"  class="row items-center justify-center">
    <example-component
      title="Math App"
      active
    ></example-component>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';
import ExampleComponent from "components/CompositionComponent.vue";


export default defineComponent({
  name: 'PageIndex',
   components: { ExampleComponent }
})
</script>