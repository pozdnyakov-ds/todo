<template>
  <TodoHeader title="Дела"></TodoHeader>

  <div style="width: 100%; text-align: justify; vertical-align: top;">
    <TodoLeft :items="items" :active="active" @clickItem="clickItem"></TodoLeft>
    <TodoMain :items="items" :active="active"></TodoMain>
  </div>
  
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoLeft from './components/TodoLeft.vue'
import TodoMain from './components/TodoMain.vue'

export default {
  data() {
    return {
      name: 'App',
      active: 0,
      items: [
        {
          id: 0,
          title: 'Заголовок 1',
          text: 'Текст 1...',
          state: 0
        },
        {
          id: 1,
          title: 'Заголовок 2',
          text: 'Текст 2...',
          state: 0
        },
        {
          id: 2,
          title: 'Заголовок 3',
          text: 'Текст 3...',
          state: 0
        },
      ]
    }
  },
  methods: {
    clickItem(id) {
      this.active = id
    }
  },
  components: {
    TodoHeader,
    TodoLeft,
    TodoMain,
}
}
</script>

<style>
body {
  margin: 0px;
  padding: 0px;
  height: 100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0px;
  padding: 0px;
}
</style>
