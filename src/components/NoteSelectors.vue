<script>
import NoteSelector from "./NoteSelector.vue";

export default {
  components: {
    NoteSelector,
  },
  data: function () {
    return {
      notes: [
        { id: 1, body: "This is a first test", timestamp: Date.now() },
        { id: 2, body: "This is a second test", timestamp: Date.now() },
        { id: 3, body: "This is a third test", timestamp: Date.now() },
        { id: 4, body: "This is a fourth test", timestamp: Date.now() },
        { id: 5, body: "This is a fifth test", timestamp: Date.now() },
        { id: 6, body: "This is a more test", timestamp: Date.now() },
      ],
      selectedNoteId: 1,
    };
  },
  methods: {
    selectNote: function (note) {
      this.selectedNoteId = note.id;
    },
  },
};
</script>

<template>
  <div class="note-selectors">
    <NoteSelector
      v-for="note in notes"
      v-bind:note="note"
      v-bind:selectedNoteId="selectedNoteId"
      v-on:selectNote="selectNote"
      v-bind:key="note.id"
    />
  </div>
</template>
