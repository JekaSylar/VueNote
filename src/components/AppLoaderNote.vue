<template>
   <div>
       <hr>
       <h3>Заметок нету...</h3>
       <app-button title="Загрузить" @click="handleLoaderNotes" />
   </div>
</template>

<script>
import AppButton from './AppButton.vue'

export default {
   
   emits: ["emitLoaderNotes"],

    components: {

    'app-button': AppButton,
    
  },

  methods: {
     handleLoaderNotes() {
        
       this.$emit('emitLoaderNotes')
     }
  },
}
</script>

<style scoped>

h3 {
    text-align: center;
}

</style>