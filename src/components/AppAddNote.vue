<template>
  <input type="text" :placeholder="placeholderString" v-model.trim="inputText"/>
           <br>
   <app-button>Добавить</app-button>
</template>

<script>
import AppButton from './AppButton.vue'

export default {
  
  components: {

    'app-button': AppButton,
  }
  
}
</script>

<style>

</style>