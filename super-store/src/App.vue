<template>
    <div id="app">
        <navbar></navbar>
        <div class="container">
            <div class="row">
                <div class="col-md-9">
                    <inventory @newItemAdded="addCartToItems" :items="items"></inventory>
                </div>
                <div class="col-md-3">
                    <card :items="card"></card>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

    import NavBar from './components/NavBar'
    import Card from './components/Card'
    import Inventory from './components/Inventory'
    import data from './data/data.js'

    export default {
        components: {
            navbar: NavBar,
            card: Card,
            inventory: Inventory
        },
        data(){
            return {
                items:[],
                card:[]
            }
        },
        mounted() {
            this.items = data
        },
        methods:{
            addCartToItems(item){
                this.card.push(item);
            }
        }
    }
</script>

<style>

    .container {
        padding-top: 10px;
    }

</style>
