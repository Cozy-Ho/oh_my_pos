<template>
<div class = "all">
  <div class = "all-content">
    <div class= "animate__animated animate__bounce animate__delay-10s">
        <b-img src="https://github.com/Cozy-Ho/oh_my_pos/blob/master/frontend/src/assets/logo.png?raw=true" fluid alt="Responsive image"></b-img>
    </div>
    <!-- 로그인 or 회원가입 컴포넌트 삽입점 -->
    <div class = "main-content">
      <component v-bind:is="sel" v-on:regist="registed">
      </component>
        <br><br>
        <!-- 로그인 컴포넌트로 가는 버튼 굳이 필요 없을듯 -->
        <!-- <b-button v-on:click="sel='Loginform'">Login</b-button>  &nbsp;&nbsp; -->
        <b-button v-on:click="sel='Loginform'">Login</b-button>  &nbsp;&nbsp;
        <b-button v-on:click="sel='Regist'">Regist</b-button> <br>
    </div>
  </div>

  
</div>
  
</template>

<script>
import Loginform from '../components/Login/Loginform.vue';
import Regist from '../components/Login/Regist.vue';


  export default {
    props: {

    },
    data: function(){
      return{
        // 초기 페이지
        sel: 'Loginform'
      }
    },
    components: {
      Loginform,
      Regist
    },
    methods:{
      registed(){
        this.sel = 'Loginform';
      }
    }
  }
</script>

<style scoped>

  .main-content {
    margin: 0px 30px 0px 30px;
    width : 200;
    background-color: white;
    
  }

  .logo {
    margin-top: 0px;
  }

  .slide-fade-enter-active {
    transition: all .3s ease;
  }
  .slide-fade-leave-active {
    transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  }
  .slide-fade-enter, .slide-fade-leave-to
  /* .slide-fade-leave-active below version 2.1.8 */ {
    transform: translateX(10px);
    opacity: 0;
  }

  .all-content {
    float : center;
    padding: 150px;
  }

</style>