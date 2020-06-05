<template>

    <div class="row">
        <div class="card" style="width: 15rem;" v-for="(item,index) in items" :key="index">
            <img :src="item.photo" class="card-img-top" alt="image" width="30%" height="40%">
            <div class="card-body">
                <h5>{{item.title}}</h5>
                <p class="card-text">{{item.price}}</p>
                <a @click="addTocart(item)" class="btn btn-info"> + Add</a>

            </div>
        </div>
    </div>


</template>

<script>
    export default {
        props: ['items'],
        methods:{
            addTocart(item){
                this.$emit('newItemAdded',item)

            }
        }
    }
</script>

<style>
</style>
