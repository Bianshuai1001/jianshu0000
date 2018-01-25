<template>
  <section class="container"v-if="error.statusCode === 404">
    <!--<nuxt-link class="button" to="/" v-if="error.statusCode === 404">-->
    <!--Homepage-->
    <div class="header">
      <img src="../assets/img/404logo.png" alt="">
    </div>
    <div class="main">
      <img src="../assets/img/404img.png" alt="">
      <h3>您要找的页面不存在</h3>
      <p>可能是因为您的链接地址有误、该文章已经被作者删除或转为私密状态。</p>
      <nuxt-link to="/">
        <input class="btn btn-success" type="button" value="返回  [简书]  主页">
      </nuxt-link>
    </div>
    <!--</nuxt-link>-->
  </section>
</template>
<script>
    export default {
        props: ['error']
    }
</script>

<style scoped>
  /*.title*/
  /*{*/
  /*margin-top: 15px;*/
  /*font-size: 5em;*/
  /*}*/
  /*.info*/
  /*{*/
  /*font-weight: 300;*/
  /*color: #9aabb1;*/
  /*margin: 0;*/
  /*}*/
  /*.button*/
  /*{*/
  /*margin-top: 50px;*/
  /*}*/
  /******************设计的404页面的样式************/
  .container .header{
    width: 100%;
    padding-top: 80px;
    padding-bottom: 20px;
  }
  .container .header img{
    position: absolute;
    left:40px;
    top:40px;
    width:300px;
  }
  .container .main{
    text-align: center;
  }
  .container .main img{
    width: 220px;
  }
  .container .main h3{
    margin: 50px 0 20px;
    font-size: 22px;
    font-weight: 800;
  }
  .container .main p{
    font-size: 14px;
    margin: 10px 0 30px;
  }
  .container .main input{
    width: 160px;
    border-radius: 40px;
    color:white;
    font-size: 15px;
    padding: 13px 0px;
    background-color: #42C02E!important;
  }
</style>

