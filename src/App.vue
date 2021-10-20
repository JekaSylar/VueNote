<template>
  <div class="card">
      <h1>{{ title }}</h1>
        <div class="form-control">
           
           <app-add-note></app-add-note>
           <app-list-note></app-list-note>
        </div>
    </div>
</template>

<script>

import AppAddNote from './components/AppAddNote.vue'
import AppListNote from './components/AppListNote.vue'

export default {
  name: 'App',
  data() {
    return {
      title: 'Заметки',
      placeholderString: "Введите заметку",
      inputText: '',
      notes: [],
    }
  },
   methods: {


   },
  components: {
    'app-list-note': AppListNote,
    'app-add-note':  AppAddNote,
  }
}
</script>

<style>

</style>
