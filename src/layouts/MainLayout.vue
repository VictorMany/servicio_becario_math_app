<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated style="height: 60px">
      <q-toolbar class="glossy">
        <q-icon size="60px" style="margin-left: -0.6rem" name="calculate">
        </q-icon>

        <q-toolbar-title class="text-white">
          <strong style="font-size: 15px">APRENDIENDO MATEMATICAS</strong>
        </q-toolbar-title>
      </q-toolbar>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>
<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "MainLayout",
});
</script>
