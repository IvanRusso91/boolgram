<template>
  <div>
    <!-- suggerimenti con rispettive icone e nomi -->
    <div class="user d-flex">
      <div class="icona">
        <img :src="user.profile_picture" :alt="user.profile_name">   
      </div>

      <div class="testo d-flex">       
        <h6>{{user.profile_name}}</h6>  
      </div>
    </div>
    <!-- /suggerimenti con rispettive icone e nomi -->
    
  </div>
</template>

<script >
export default {
  name: 'BloccoSuggerimenti',
   props:{
    user: Object,
  },
}
</script>

<style lang="scss" scoped>

  @import '../assets/style/mixin';

  .user{
    .icona{  
      img{
        width: 55px;
        height: 55px;
        border-radius: 50%;
        margin: 0 0 20px 30px;
      }
    }
    .testo{
      justify-content: space-between;
      margin: 15px 0 0 15px;
    }  
  } 
  
  
</style>