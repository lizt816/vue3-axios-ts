<template>
  <div class="home">
    <button @click="a('GET')">get</button>
    <button @click="a('POST')">post</button>
  </div>
</template>

<script lang="ts">
import { ref } from 'vue';
import q from '../utils/xhr';
export default {
  name: 'HomeView',
  setup(){
       function a(m:string){
        q.axios({
          method:m,
          url:"http://localhost:3000/posts",
          data:{
            id:1,
            title:"涛少",
            author:"123456"
          }
        }).then(res=>{
          console.log(res,"000")
        })
       }
      return{
        a
      }
  }
};
</script>
