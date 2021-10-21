<template>
<div>
  <ul class="list">
              <li class="list-item">
                
                Заметка

                
                <app-button color="danger" title = "Удалить" />

              </li>
                     
          </ul>
          <app-count-note/>
          <div >Заметок пока нет. Добавьте первую</div>
</div>          
</template>

<script>
import AppButton from './AppButton.vue'
import AppCountNote from './AppCountNote.vue'

export default {

    components: {

    'app-button': AppButton,
    'app-count-note': AppCountNote,
  },

}
</script>

<style>

</style>