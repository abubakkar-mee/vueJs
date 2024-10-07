<script>
export default{
    data(){
        return {
            todos:['earn money','buy phone','ride bike'],
            search:'',
            newTodo:"",
    
        }
    },
    methods:{
        addTodo(){
            this.todos.push(this.newTodo)
            this.newTodo = ''
        }
    },
    computed:{
        filteredItem(){
            if(this.search.length >=3){
                return this.todos.filter((todo)=>todo.includes(this.search))
            }else{
                return this.todos
            }
        }
    }
}

</script>

<template>
<input type="text" placeholder="search" v-model="search">
<p v-for="todo in filteredItem">{{ todo }}</p>
<input placeholder="type here" type="text" v-model="newTodo">
<button @click="addTodo">Add</button>
</template>

<style>
    p{
        color: rgb(119, 214, 176);
        font-weight: bold;
        font-size: 12px;
        text-align: center;
    }
    input{
        display: block;
        margin: 0 auto;
        padding: 10px 10px;
        width: 30%;
        border-radius: 5px;
        border: none;
        outline: none;
        background-color: rgb(212, 241, 229);
        color: black;
        font-weight: bold;
    }
    input:focus{
        border:2px solid rgb(119, 214, 176);
    }
    button{
        display: block;
        margin:0 auto;
        margin-top: 16px;
        width: 30%;
        padding: 10px;
        border-radius: 5px;
        border:none;
        cursor: pointer;
        background-color: rgb(1, 112, 68);
        font-weight: bold;
        transition: all .2s ease;
    }
    button:active{
        transform: scale(0.9);
    }
</style>



