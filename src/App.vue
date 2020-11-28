<template>
  <div id="app">
    <Home v-if="!isLogin"></Home>
    <Editor v-if="isLogin" :user="userDate"></Editor>
  </div>
</template>

<script>
import Home from "./components/Home"
import Editor from "./components/Editor"
  
export default {
  name:app,

  data(){
    return{
      isLogin: false,
      userDate: null
    }
  },
  components:{
    Home:Home,
    Editor:Editor
  },
    created(){
    firebase.auth().onAuthStateChanged( (user) => {
      console.log(user);
      if(user){
        this.isLogin = true;
        this.userDate = user;
      }else{
        this.isLogin = false;
        this.userDate = null;
      };
    });
  }
}
</script>

<style>

</style>