<template>
	<div>{{grandsonData.name}}</div>
</template>

<script>
  export default {
    name: "Grandson",
    props:{
      grandsonData:Object
    }
  }
</script>

<style scoped>
div{
  background-color: brown;
}
</style>
