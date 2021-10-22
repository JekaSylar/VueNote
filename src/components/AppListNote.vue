<template>
<div>
  <ul class="list">
              <li class="list-item" v-for="note in notes" :key="note.id">
                
                 {{ note.text  }}
                
                <app-button color="danger" title = "Удалить" />

              </li>
                     
          </ul>
          <app-count-note/>
         
</div>          
</template>

<script>
import AppButton from './AppButton.vue'
import AppCountNote from './AppCountNote.vue'

export default {

  props: ['notes'],

    components: {

    'app-button': AppButton,
    'app-count-note': AppCountNote,
  },

}
</script>

<style>

</style>