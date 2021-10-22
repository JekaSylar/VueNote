<template>
  <button class="btn" :class="color">
    {{ title }}
  </button>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      default: "",
      validator(value) {
        return ["", "danger"].includes(value);
      },
    },
    title: {
      type: String,
      required: true,
    },
  },
};
</script>

<style>
</style>