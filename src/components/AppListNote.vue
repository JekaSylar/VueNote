<template>
<div>
  <ul class="list">
              <li class="list-item">
                
                Заметка

                
                <app-button color="danger">Удалить</app-button>

              </li>
              <hr />
       
          </ul>
          <div >Заметок пока нет. Добавьте первую</div>
</div>          
</template>

<script>
import AppButton from './AppButton.vue'

export default {

    components: {

    'app-button': AppButton,
  },

}
</script>

<style>

</style>