<template>
  <TodoHeader title="Дела"></TodoHeader>
  <div>
    <div style="width: 25%; height: 100%; background-color: antiquewhite;"></div>
    <div style="width: 75%; height: 100%; background-color: #fff;"></div>
  </div>
  
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'

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
    TodoHeader
  }
}
</script>

<style>
body {
  margin: 0px;
  padding: 0px;
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
