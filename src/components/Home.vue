<template>
  <div id="home">
      <h1>{{msg}}</h1>
      <button @click="googleLogin">Googleアカウントでログイン</button>
  </div>
</template>

<script>

export default {
    name:"home",

    data(){
        return{
            msg: "Welcome"
        }
    },
    methods:{
        googleLogin:function(){
            var provider = new firebase.auth.GoogleAuthProvider();
            firebase.auth().signInWithRedirect(provider);
        }
    }
}
</script>

<style>

</style>