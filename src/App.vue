<template>
  <TodoHeader title="Дела"></TodoHeader>
  <TodoForms @loadArticles="loadArticles"></TodoForms>
  <div style="width: 100%; text-align: justify; vertical-align: top;">
    <TodoLeft 
      :items="items" 
      :active="active" 
      @clickItem="clickItem"
      @deleteItem="deleteItem"
      ></TodoLeft>
    <TodoMain :items="items" :active="active"></TodoMain>
  </div>
  
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoLeft from './components/TodoLeft.vue'
import TodoMain from './components/TodoMain.vue'
import TodoForms from './components/TodoForms.vue'
import axios from 'axios'

export default {
  data() {
    return {
      name: 'App',
      active: 0,
      items: [],
    }
  },
  methods: {
    clickItem(id) {
      this.active = id
    },
    async loadArticles() {
      axios.get('https://todo-77cd5-default-rtdb.europe-west1.firebasedatabase.app/articles.json')
        .then(response => {
          this.items = (response.data == null) ? [] : Object.keys(response.data).map(key => {
            return {
              id: key,
              title: response.data[key].title,
              textBody: response.data[key].textBody,
              status: response.data[key].status
            }
          })
          console.log('ITEMS: ', this.items)
          //this.items = response.data 
        })
    },
    async deleteItem(id) {
      console.log('Delete: ', id)
      await axios.delete('https://todo-77cd5-default-rtdb.europe-west1.firebasedatabase.app/articles/' + id + '.json')
      //this.loadArticles()
      this.items = this.items.filter(item => item.id !== id)
    },
  },
  components: {
    TodoHeader,
    TodoLeft,
    TodoMain,
    TodoForms,
  },
  mounted: function() {
    this.loadArticles()
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
