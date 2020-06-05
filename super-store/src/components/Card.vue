<template>
      <ul class="list-group">
          <li class="list-group-item">
              <span>Name</span>
              <span class="float-lg-right">Price</span>
          </li>
          <hr>
          <li class="list-group-item" v-for="(item,index) in items" :key="index">
              <span> {{ item.title }} </span>
              <span class="float-lg-right">{{ item.price }}
                     <a @click="removeItem(item)" class="btn btn-danger">X</a>
              </span>
          </li>
          <hr>
          <li class="list-group-item">
              <span>Total-Price</span>
              <span class="float-lg-right">{{totalPrice}}</span>
          </li>
     </ul>   
  </template>

  <script>
  export default {
      props:['items'],
      computed:{
        totalPrice(){
          var total = 0;
          this.items.forEach(item=>{
              console.log(item.price);
              total = parseFloat(total) + parseFloat(item.price);
          })
            return total;
        }
      },
      methods:{
          removeItem:function (index) {
              this.items.splice(index, 1);
          }
      }
  }
  </script>


  <style>

  </style>
