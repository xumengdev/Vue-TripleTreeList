<template>
  <div class="tree-toot">
    <div v-for="(parentsD,index) in parentsDatas" :key="index">
      <Parents :parentsData="parentsD" v-on:ChangeP="showOr"></Parents>
    </div>
  </div>
</template>

<script>
  import Parents from "./components/Parents"
  export default {
    name: "Tree",
    components:{
      Parents,
    },
    data(){
      return{
        initShow:false,
        parentsDatas:[
          {
            name: "p1",
            data: [],
            childsData: [{
              name: "Ch01",
              isShow:this.initShow,
              grandsonData: [{
                name: "gson01",
                data: [],
                isShow:this.initShow
              }, {
                name: "gson02",
                data: [],
                isShow:this.initShow
              }],
            }, {
              name: "Ch02",
              isShow:this.initShow,
              grandsonData: [{
                name: "gson03",
                data: [],
                isShow:this.initShow
              }, {
                name: "gson04",
                data: [],
                isShow:this.initShow
              }],
            }]
          },
          {
            name: "p2",
            data: [],
            childsData: [{
              name: "Ch03",
              isShow:this.initShow,
              grandsonData: [{
                name: "gson05",
                data: [],
                isShow:this.initShow
              }, {
                name: "gson06",
                data: [],
                isShow:this.initShow
              }],
            }, {
              name: "Ch04",
              isShow:this.initShow,
              grandsonData: [{
                name: "gson07",
                data: [],
                isShow:this.initShow
              }, {
                name: "gson08",
                data: [],
                isShow:this.initShow
              }],
            }]
          }]
      }
    },
    methods:{
      showOr(name){
        this.parentsDatas.forEach(function (item) {
          if (item.name == name) {
            item.childsData.forEach(function (item1) {
              item1.isShow = !item1.isShow

            })
          }

        })
      }
    }

  }
</script>

<style scoped>
  .tree-toot{
    font-size: 40px;
    background-color: #cacaca;
  }

</style>
