<template>
  <!-- new note -->
  <div class="new-note">
    <label>Title</label>
    <input v-model="note.title" type="text">
    <label>Description</label>
    <textarea v-model="note.descr"></textarea>
    <div class="option-list">
      <input class="priority" type="radio" id="radioStandart" value="Standart" v-model="note.priority">
      <label for="radioStandart">Standart</label>
      <input class="priority" type="radio" id="radioImportant" value="Important" v-model="note.priority">
      <label for="radioImportant">Important</label>
      <input class="priority" type="radio" id="radioVeryImportant" value="Very Important" v-model="note.priority">
      <label for="radioVeryImportant">Very Important</label>
    </div>
    <button class="btn btnPrimary" @click="addNote">New note</button>
  </div>
</template>

<script>
export default {
  props: {
    note: {
      type: Object,
      required: true
    }
  },
  methods: {
    addNote () {
      this.$emit('addNote', this.note)
		}
  }
}
</script>

<style lang="scss">
.new-note {
  text-align: center;
}
.option-list {
  display: flex;
  margin: 20px 0;
  .priority {
    margin-right: 12px;
    font-weight: bold;
  }
  label {
    margin-right: 20px;
    &:last-child {
      margin-right: 0;
    }
  }
}
</style>
