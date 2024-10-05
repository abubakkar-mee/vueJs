<script>
export default {
  data(){
    return{
      title:'hi title',
      name:'',
      email:'',
      list:['tvs','yamaha','bajaj','suzuki','honda','hero'],
      todos:[],
      newtodo:'',
      rgbColor:''
    }
  },
  methods:{
    addTodo(){
      if(this.newtodo !== ""){
        this.todos.push(this.newtodo)
        this.newtodo = ''
      }
    },
    deleteLast(){
      this.todos.pop()
    },
    changeColor(){
      const red = Math.floor(Math.random() * 255);
      const green = Math.floor(Math.random() * 255);
      const blue = Math.floor(Math.random() * 255);
      this.rgbColor = `rgb(${red},${green},${blue})`
      console.log(this.rgbColor)
    }
  }
}
</script>

<template>
  <h2>{{ title }}</h2>
  <input :style="{backgroundColor:rgbColor}" type="text" v-model="name">
  <input type="text" v-model="email">
  <p>Your name is {{ name }}</p>
  <p>Your mail is {{ email }}</p>
  <ul>
    <li v-for="(bike,index) in list" :key="index">{{ bike }}</li>
  </ul>
  <p v-for="todo in todos">{{ todo }}</p>
  <input type="text" v-model="newtodo">
  <button @click="addTodo">add todo</button>
  <button @click="deleteLast">delete last</button>
  <button @mouseover="changeColor">Change Color</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
