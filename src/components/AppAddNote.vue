<template>
  <input
    type="text"
    :placeholder="placeholderString"
    v-model.trim="inputText"
  />

  <br />
  <app-button title="Добавить" @click="handleNotes" />
</template>

<script>
import AppButton from "./AppButton.vue";

export default {
  props: ["placeholderString"],
  emits: ["emitNotes"],
  data() {
    return {
      inputText: "",
    };
  },

  components: {
    "app-button": AppButton,
  },

  methods: {
    handleNotes() {
      this.$emit("emitNotes", this.inputText);
    },
  },
};
</script>

<style>
</style>