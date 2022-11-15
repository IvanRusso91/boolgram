<template>
  <div class="box d-flex">
    <!-- loading.. -->
    <dir v-if="isLoading" class="loading">
      <LoadingComp />
    </dir>
    <!-- /loading.. -->

    <div v-else class="box-left d-flex">

      <!-- Storie -->
      <div class="box-storie">


        <div class="bs d-flex">
        <BloccoStorie 
          :user= 'user' 
          v-for="(user, index) in userArray" :key="`a-${index}`"/>

        </div>

      </div>
      <!-- /Storie -->


      <!-- Post -->
      <div class="box-post ">
        <BloccoPost 
        :posts= 'posts'
        v-for="(posts, index) in postArray.slice(0,nPost)" :key="`b-${index}`"/>
      </div>

      <div  class="loadMore" v-if="postArray.length > nPost  " >
        <button class="btn " @click= "loadMore()" >Load More <i class="fa-solid fa-arrow-down"></i></button>
      </div>

      <div class="loadMore" v-else>
        <button class="btn " @click= "loadLess(post)" >Load Less <i class="fa-solid fa-arrow-up"></i></button>
      </div>
      <!-- /Post -->

    </div>
    <!-- loading.. -->
    <div v-if="isLoading">
      <LoadingRight />
    </div>
    <!-- /loading.. -->

    <!-- Blocco di destra con profilo, suggerimenti e Footer -->
    <div v-else class="container-fluid box-right">
      <div  class=" box-profilo">
        <BloccoProfilo />

        <div class="suggeriti">
          <h6 class="sug-left">Suggeriti per te</h6>
          <h6 class="mt">Mostra tutti</h6>
        </div>

        <BloccoSuggerimenti 
         :user= 'user' 
          v-for="(user, index) in userArray" :key="`a-${index}`"/>
        
        <FooterComp />
      </div>
    </div>
    <!-- Blocco di destra con profilo, suggerimenti e Footer -->

  </div>
  
</template>

<script>

import BloccoStorie from '@/components/BloccoStorie';
import BloccoPost from '@/components/BloccoPost';
import BloccoProfilo from '@/components/BloccoProfilo';
import BloccoSuggerimenti from '@/components/BloccoSuggerimenti';
import FooterComp from '@/components/FooterComp';
import LoadingComp from '@/components/LoadingComp';
import LoadingRight from '@/components/LoadingRight';
import axios from 'axios';

export default {
  name : 'MainComp',
  components:{
    BloccoStorie,
    BloccoPost,
    BloccoProfilo,
    BloccoSuggerimenti,
    FooterComp,
    LoadingComp,
    LoadingRight,
  },
  data(){
    return{
      userUrl: 'https://flynn.boolean.careers/exercises/api/boolgram/profiles',
      userArray: [],
      user : '',
  
      postUrl: 'https://flynn.boolean.careers/exercises/api/boolgram/posts',
      postArray: [],
      posts : '',

      isLoading: true,
      nPost: 2,
      i:2,
       
    }
  },

  mounted(){
    this.getAPI();
    this.getPostAPI();
  },

  methods:{
    getAPI(){
      axios.get(this.userUrl)
      .then(r =>{
        this.userArray = r.data
        
        setTimeout(()=>{
         this.isLoading = false;
       },1000)
      })
    },

    getPostAPI(){
      axios.get(this.postUrl)
      .then(e =>{
        this.postArray = e.data;
        
      })
    },

    // serve a caricare più post
    loadMore(){
     this.nPost += this.i;
    },
    
    loadLess(){
      this.nPost -= (this.postArray.length - 2) ;
    },
  }
}

</script>

<style lang="scss" scoped>

@import '../assets/style/mixin';

.box{
  margin-top: 77px; 
  .box-left{
    width: 65%;
    flex-direction: column;
    .loadMore{
      text-align: center;
      margin-top: -20px;
    }  
    .box-storie{
      border: 1px solid rgb(192, 192, 192);
      margin-top: 50px;
      background-color: white;
      .bs{
        overflow-y: hidden;
        padding: 20px 0 20px 20px;
        &::-webkit-scrollbar {  
          height: 5px;
        }
        &::-webkit-scrollbar-track {
          border-radius: 5px;
        }
        &::-webkit-scrollbar-thumb {
          background: linear-gradient(to right,#b100f7,#c13ff5, #c777e7);
          border-radius: 10px;
        }
      }
      .loading{
        text-align: center;
        margin-top: 20px;
      }
       
    }    
  }
  .box-right{
    display: flex;
    position: fixed;
    left: 60%;
    width: 25%;
    
    .suggeriti{
      display: flex;
      justify-content: space-between;
      margin: 80px 0  20px 30px;
      .sug-left{
        color: rgb(192, 192, 192);
      }
      
    }
    .box-profilo{
      margin-top: 50px;
      width: 100%;
      
    }
    
  }
}

  // MQ

  @media screen and (min-width: 500px) and (max-width: 991px) {
      
      .mt{
        display: none;
      }
    
  }

  @media screen and (min-width: 992px) and (max-width: 1800px) {
      
      .box-profilo{
        margin-left: 30px;
      }
    
  }

</style>