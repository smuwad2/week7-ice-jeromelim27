<script>
    export default { 
        // Add code in appropriate places
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
                item_add: ""
            }
            
        },
        methods:{
            remove(item){
                this.items = this.items.filter( x => x != item)
            },
            add(){
                console.log(this.item_add)
                this.items.push(this.item_add)
            }
        }
    }
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
     <ul>
        <li v-for="item in items">{{item}}<button v-on:click="remove(item)" style="color:black;background:lightgrey;margin-left:5px">Delete!</button></li>
     </ul>

     <input v-model="item_add" style="color:black;background:white"></input><button @click="add" style="color:white;background:grey">Add!</button>
   
</template>
