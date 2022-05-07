<template>
  <TodoHeader title="Дела"></TodoHeader>

  <div style="width: 100%; text-align: justify; vertical-align: top;">
    <TodoLeft :items="items"></TodoLeft>
    <div style="margin: 5px; background-color: #fff; 
      display: inline-block; padding: 10px; vertical-align: top;"
    >Основной блок</div>
  </div>
  
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoLeft from './components/TodoLeft.vue'

export default {
  data() {
    return {
      name: 'App',
      items: [
        {
          id: 1,
          title: 'Заголовок 1',
          text: 'Текст 1...',
          state: 0
        },
        {
          id: 2,
          title: 'Заголовок 2',
          text: 'Текст 2...',
          state: 0
        },
        {
          id: 3,
          title: 'Заголовок 3',
          text: 'Текст 3...',
          state: 0
        },
      ]
    }
  },
  components: {
    TodoHeader, TodoLeft
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
