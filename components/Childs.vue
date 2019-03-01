<template>
<div>
  <div @click="sendMethod">{{childsData.name}}</div>
  <div v-for="grandsonData in childsData.grandsonData">
    <Grandson v-bind:grandsonData="grandsonData" v-show="grandsonData.isShow"></Grandson>
  </div>
</div>
</template>

<script>
  import Grandson from "./Grandson"
  export default {
    name: "Childs",
    props:{
      childsData:Object
    },
    data(){
      return{
      }
    },
    components:{
      Grandson
    },
    methods:{
      sendMethod(){
        let name = this.childsData.name
        console.log(name)
        this.$emit('ChangeC', name)
      }
    }

  }
</script>

<style scoped>
div{
  background-color: palegreen;
}
</style>
