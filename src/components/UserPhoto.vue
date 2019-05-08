<template>
  <div>
    <div class="photo">头像</div>
    <div class="name">姓名：{{name}}</div>
    <div class="no">工号：{{no}}</div>
  </div>
</template>

<script>
  export default {
    name: "UserPhoto",
    props : {
      name: String,
      no: String
    },

    data(){
      return {
        name2: '111'
      }
    },

    mounted() {
      this.name2 = '222'
      this.name = '333'
    }
  }
</script>

<style scoped>

</style>
