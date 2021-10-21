<template>
  <div class="card">
    <h1>{{ title }}</h1>
    <div class="form-control">
      <app-add-note
        :placeholderString="placeholderString"
        @emitNotes="createNote"
      />
      <app-list-note />
    </div>
  </div>
</template>

<script>
import AppAddNote from "./components/AppAddNote.vue";
import AppListNote from "./components/AppListNote.vue";
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      title: "Заметки",
      placeholderString: "Введите заметку",
      notes: [],
    };
  },
  methods: {
    async createNote(value) {
      console.log(value);

      const res = await axios.post(
        "https://notes-c3c48-default-rtdb.firebaseio.com/notes.json",
        {}
      );

      console.log(res);
    },

    LoaderNote() {},
  },
  components: {
    "app-list-note": AppListNote,
    "app-add-note": AppAddNote,
  },
};
</script>

<style>
</style>
