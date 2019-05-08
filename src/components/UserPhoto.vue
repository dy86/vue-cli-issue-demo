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
    }
  }
</script>

<style scoped>

</style>
