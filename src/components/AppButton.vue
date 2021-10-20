<template>
  <button class="btn" :class="color" >
      <slot />
  </button>
</template>

<script>


export default {

 props: {
    color: {
      type: String,
      default: '',
      validator(value) {
        return ['', 'danger'].includes(value)
      }
    }
  },
 
 data() {
   
  },

}
</script>

<style>

</style>