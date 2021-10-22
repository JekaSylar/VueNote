<template>
  <div class="card">
    <h1>{{ title }}</h1>
    <div class="form-control">
      <app-add-note
        :placeholderString="placeholderString"
        @emitNotes="createNote"
      />
      <app-list-note v-if="notes.length !== 0"
      
        :notes="notes"
       />


      <app-loader-note 
          v-if="notes.length === 0"
          @emitLoaderNotes = "LoaderNote"
      />
    </div>
  </div>
</template>

<script>
import AppAddNote from "./components/AppAddNote.vue";
import AppListNote from "./components/AppListNote.vue";
import AppLoaderNote from "./components/AppLoaderNote.vue";
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      title: "Заметки",
      placeholderString: "Введите заметку",
      notes: [],
      dataBase: "https://notes-c3c48-default-rtdb.firebaseio.com/notes.json",
    };
  },
  methods: {
    async createNote(value) {
      
      await axios.post(
        this.dataBase,
        {
          text: value,
        }
      );

    
    },

    async LoaderNote() {
     
  
     const {data} = await axios.get(this.dataBase)

     this.notes = Object.keys(data).map(key => {
            return {
              id: key,
              ...data[key]
            }
          })

     console.log(this.notes)
    },
  },
  components: {
    "app-list-note": AppListNote,
    "app-add-note": AppAddNote,
    "app-loader-note" : AppLoaderNote
  },
};
</script>

<style>
</style>
