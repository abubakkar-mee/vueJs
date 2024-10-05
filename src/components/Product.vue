<script>
export default {
    data(){
        return{
            products:[
                {title:"iphone",price:125,details:"it's awesome product"},
                {title:"samsung",price:135,details:"it's awesome product"},
                {title:"vivo",price:110,details:"it's awesome product"},
                {title:"xaomi",price:120,details:"it's awesome product"},
                {title:"redmi",price:75,details:"it's awesome product"},
            ]
        }
    },
    methods:{
        addProduct(){
            this.products.push({title:"one plus",price:95,details:"probles of green lines"})
        },
        removeProduct(){
            this.products.pop()
        }
    }
}
</script>


<template>
    <button @click="addProduct">Add product</button>
    <button @click="removeProduct">Remove product</button>
    <main>
        <div v-for="product in products" class="product-container">
            <p>{{ product.title }}</p>
            <p>{{ product.price }}</p>
            <p>{{ product.details }}</p>
       </div>
    </main>
</template>

<style scoped>

main{
    width: 90%;
    margin: 0 auto;
    display: flex;
    gap: 15px;
    flex-wrap: wrap;
}

.product-container{
    border: 2px solid rgb(19, 117, 83);
    width: 300px;
    padding: 20px;
    border-radius: 8PX;
    transition: all .1s ease;
}
.product-container:hover{
    transform: scale(1.05);
}

</style>