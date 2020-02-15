<template>
  <div class="card">
    <img src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png" class="image">
    <div class="con">
      <div>姓名：李</div>
      <div>身份：总管理员</div>
      <time class="time">{{ currentDate }}</time>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dashboard',
  data() {
    return {
      currentDate: new Date()
    };
  }
}
</script>

<style lang="scss" scoped>
.card {
  width: 50%;
  height: 400px;
  border: 1px solid #F0F0F0;
  margin: auto;
  margin-top: 10%;
  padding-top: 5%;
}
  .image {
    width: 150px;
    height: 150px;
    border-radius:250px;
    display: block;
    margin: auto;
    margin-bottom: 5%;
    margin-top: 2%;
  }
  .con {
    text-align: center;
    line-height: 30px;  
  }
    .time {
        font-size: 13px;
        color: #999;
      }
  
  

</style>
