<template>
  <!-- blocco più alto del main dove stanno le icone e i nomi per le storie -->
  <div class="story-users">
    <img :src="user.profile_picture" :alt="user.profile_name">
    <h6>{{shortifyContent(user.profile_name)}}</h6>  
  </div>
 
  <!-- blocco più alto del main dove stanno le icone e i nomi per le storie -->

</template>

<script>
export default {
  name : 'BloccoStorie',
  props:{
    user: Object,
    
  },
  methods:{
    // funzioncina per ridurre la lunghezza dei nomi    
    shortifyContent(text){
            return text.substring(1, 7)+ '...';
    },
  }
}

</script>

<style lang="scss" scoped>

@import '../assets/style/mixin';

.story-users{
  margin-right: 35px;
  text-align: center;  
  img{
    border: 2px solid rgb(156, 11, 144);
    padding: 2px;
    width: 55px;
    height: 55px;
    border-radius: 50%;
  }
}

</style>