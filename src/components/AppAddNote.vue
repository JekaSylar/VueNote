<template>
  <input 
      type="text" 
      :placeholder="placeholderString"
      v-model.trim="inputText"
  />

           <br>
   <app-button title = "Добавить" />
</template>

<script>
import AppButton from './AppButton.vue'

export default {

  props: ['placeholderString'],

  data() {
    return {

      inputText: '',
    
    }
  },
  
  components: {

    'app-button': AppButton,
  },

   methods: {

     
     

   }
  
}
</script>

<style>

</style>