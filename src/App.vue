<template>
  <div class='header'>
    <div class='header__header'>
      <p>To Do List</p>
      <div class='header__info--block'>
        <div class='header__block' v-for='(item, index) of currentValue' :key='index'>
          <span class='header__text'>{{ item.text }}</span>
          <span id='scope-value' class='header__value'>{{ item.value }}</span>
        </div>
      </div>
      <button class='header__button' type='button'></button>
    </div>
    <main-layout>
      <toDoList v-for='list of toDoLists' :key='list.id' :id='list.id' :text='list.text' :date='list.date' />
    </main-layout>
  </div>
</template>
<script>
export default {
  name: 'App',
  components: {
    MainLayout: () => import('@/layouts/MainLayout.vue'),
    toDoList: () => import('@/components/toDoList.vue')
  },
  data() {
    return {
      toDoLists: [
        {
          id: 0,
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          date: '2021-01-03T10:20:04.400Z',
          completed: false
        },
        {
          id: 1,
          text: 'Create main page of todolistfor frontend test task',
          date: '2021-01-03T10:20:04.400Z',
          completed: true
        },
        {
          id: 2,
          text: 'Create main page of todolistfor frontend test task',
          date: '2021-01-03T10:20:04.400Z',
          completed: true
        },
        {
          id: 3,
          text: 'Create main page of todolistfor frontend test task',
          date: '2021-01-03T10:20:04.400Z',
          completed: true
        },
        {
          id: 4,
          text: 'Create main page of todolistfor frontend test task',
          date: '2021-01-03T10:20:04.400Z',
          completed: true
        },
        {
          id: 5,
          text: 'Create main page of todolistfor frontend test task',
          date: '2021-01-03T10:20:04.400Z',
          completed: true
        }
      ]
    }
  },
  computed: {
    currentValue() {
      let toDoLength = this.toDoLists.length
      let completedArr = this.toDoLists.filter(el => !el.completed)
      let sucessful = this.toDoLists.filter(el => el.completed)
      let toDoActive = completedArr.length
      let toDoSucessful = sucessful.length
      return [
        {
          text: 'Scope',
          value: toDoLength
        },
        {
          text: 'Active',
          value: toDoActive
        },
        {
          text: 'Successful',
          value: toDoSucessful
        }
      ]

    }
  }
}
</script>

<style>
</style>
