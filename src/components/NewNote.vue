<template>
  <!-- new note -->
  <div class="new-note">
    <label>Title</label>
    <input v-model="note.title" type="text">
    <label>Description</label>
    <textarea v-model="note.descr"></textarea>
    <div class="option-list">
			<label>Standart</label>
      <input class="priority" type="radio" value="standart" v-model="note.priority">
      <label>Important</label>
      <input class="priority" type="radio" value="important" v-model="note.priority">
      <label>Very Important</label>
      <input class="priority" type="radio" value="veryImportant" v-model="note.priority">
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
	align-items: center;
  .priority {
    margin: 0 12px 0 0;
    font-weight: bold;
		height: 20px;
		width: 20px;
  }
  label {
    margin: 0 20px 0 0;
		box-shadow: none;
    &:last-child {
      margin-right: 0;
    }
  }
}
</style>
