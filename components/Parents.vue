<template>
  <div>
    <p @click="sendMethed">{{parentsData.name}}</p>
    <div v-for="(childsData,index) in parentsData.childsData" :key="index">
      <Childs v-bind:childsData="childsData" v-show="childsData.isShow" v-on:ChangeC="showOr"></Childs>
    </div>
  </div>
</template>

<script>
  import Childs from './Childs'
  export default {
    name: "Parents",
    props:{
      parentsData:Object
    },
    data() {
      return{
      }
    },
    components: {
      Childs
    },
    methods:{
      sendMethed(){
        let name = this.parentsData.name
        this.$emit('ChangeP', name)
      },
      showOr(name){
        this.parentsData.childsData.forEach(function (item) {
          if (item.name == name) {
            item.grandsonData.forEach(function (item1) {
              item1.isShow = !item1.isShow
            })

          }

        })
      }

    }
  }
</script>

<style scoped>
div{
  background-color: #25a4bb;
  width: 20vw;
}
</style>
