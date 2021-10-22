<template>
<div>
  <ul class="list">
              <li class="list-item" v-for="(note, idx) in notes" :key="note.id">
                
                 {{ idx+1 }}. {{  note.text  }} 
                
                <app-button 
                            color="danger" 
                            title = "Удалить"
                            @click="handleDelete(note.id)" 
                />

              </li>
                     
          </ul>

          <hr>    
          <app-count-note :noteCount="this.notes.length" />
         
</div> 
     
</template>

<script>
import AppButton from './AppButton.vue'
import AppCountNote from './AppCountNote.vue'

export default {

  props: ['notes'],
   emits: ["emitDeleteNotes"],

    components: {

    'app-button': AppButton,
    'app-count-note': AppCountNote,
  },

   methods: {
    handleDelete(id) {
 
       
      this.$emit("emitDeleteNotes", id);
    },
  },
  
}
</script>

<style>

</style>