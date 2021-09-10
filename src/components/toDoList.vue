<template>
  <div>
    <input type="checkbox" class="custom-checkbox" :id="id">
    <label class="list-block__label" :for="id"></label>
    <span></span>
    <p v-if='text'>{{ text }}</p>
    <input v-else placeholder='Please enter task description' type='text'>
  </div>
</template>

<script>
export default {
  name: 'toDoList',
  props: {
    id: {
      type: Number,
      default: 0
    },
    date: {
      type: String,
      default: '3 Jan 2021'
    },
    text: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped>

</style>