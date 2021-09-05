<template>
  <div>
    <q-item
      :class="'bg-' + color"
      style="border-radius: 0.5rem; margin: 0.5rem; font-weight: bold"
      clickable
      tag="a"
      @click="openDialog(questionDialog)"
    >
      <q-item-section v-if="icon" avatar>
        <q-icon :name="icon" />
      </q-item-section>

      <q-item-section>
        <q-item-label style="font-weight: bold">{{ title }}</q-item-label>
        <q-item-label caption>
          {{ caption }}
        </q-item-label>
      </q-item-section>
    </q-item>

    <q-dialog
      v-model="colors"
      transition-show="rotate"
      transition-hide="rotate"
    >
      <sumas-component-questions></sumas-component-questions>
    </q-dialog>
  </div>
</template>

<script>
import SumasComponentQuestions from "./colorsComponent/SumasComponentQuestions.vue";

export default defineComponent({
  name: "EssentialLink",
  components: {
    SumasComponentQuestions,
  },
  props: {
    title: {
      type: String,
      required: true,
    },

    caption: {
      type: String,
      default: "",
    },

    color: {
      type: String,
      default: "#",
    },

    icon: {
      type: String,
      default: "",
    },

    questionDialog: {
      type: String,
      default: "",
    },
  },

  data() {
    return {
      numbers: false,
      colors: false,
      alphabet: false,
      pronouns: false,
      phrases: false,
      fruits: false,
      actions: false,
      parts: false
    };
  },
  methods: {
    openDialog(questionDialog) {
      console.log(questionDialog);
      switch (questionDialog) {
        case "numbers":
          this.numbers = true;
          break;
        case "colors":
          this.colors = true;
          break;
        case "alphabet":
          this.alphabet = true;
          break;
        case "pronouns":
          this.pronouns = true;
          break;
        case "phrases":
          this.phrases = true;
          break;
        case "fruits":
          this.fruits = true;
          break;
        case "actions":
          this.actions = true;
          break;
        case "body":
          this.parts = true;
          break;
      }
    },
  },
});
</script>

<style lang="sass" scoped>
.button
  color: $blue
  padding: 0.3rem
  margin: 0.2rem

.q-btn
  width: 30%
  height: 70px
  margin-bottom: 0.5rem
  padding-top: 0.3rem

.q-item:hover
  transform: scale(1.05)
  transition: .2s
  z-index: 1000

h6
  margin-top: -0.5rem
</style>
