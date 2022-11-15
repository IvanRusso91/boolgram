<template>
  <div class="box-post">
    <div  class="user-post d-flex">
      <!-- Parte più alta del post con dentro le info dell'utente che pubblica -->
      <div class="header-post d-flex">

        <section class="icona">
          <img :src="posts.profile_picture" :alt="posts.profile_name">
        </section>

        <section class="testo">
          <h6>{{posts.profile_name}}</h6>
          <p>{{posts.date.date}}</p>
        </section>

      </div>
      <!-- /Parte più alta del post con dentro le info dell'utente che pubblica -->

      <div class="post">
        <!-- Img del post con annesso testo e 2 icone  -->
        <section class="p-img">
          <img :src="posts.post_image" :alt="posts.profile_name">
        </section>

        <section class="p-test">
          <h5>
          <i class="fa-regular fa-heart"></i>
          <i class="fa-regular fa-comment"></i>{{posts.post_text}}</h5>         
        </section>
        <!-- /Img del post con annesso testo e 2 icone  -->
        
        <!-- sezione Like -->
        <section>
          <div class="d-flex like" v-for="item in posts.likes.slice(0,1)" :key="`a:${item}`">
            <div class="user">
              <img :src="item.profile_picture" :alt="item.username">
            </div>
            <p>Piace <strong>{{item.username}}</strong> e <strong>{{posts.likes.length}}</strong> altri </p>

          </div>
        </section>
        <!-- /sezione Like -->
        
        <!-- sezione commenti -->
        <section>
          
          <div v-if="posts.comments.length > nCommenti  " >
            <button class="btn loadMore" @click= "loadMore(posts)" >mostra tutti e {{posts.comments.length}} i commenti <i class="fa-solid fa-arrow-down"></i></button>
          </div>      

          <div v-else-if="posts.comments.length <= i "></div>

          <div v-else>
            <button class="btn loadMore" @click= "loadLess()" >Carica meno commenti <i class="fa-solid fa-arrow-up"></i></button>
          </div>
          <ul>
            <li 
              class="d-flex commenti"
              v-for="item in posts.comments.slice(0,nCommenti)" 
              :key="`a:${item}`">

              <h6>{{item.username}} :</h6> 
              <span>{{item.text}}</span>
            </li>
          </ul>
          
        

        </section>
        <!-- /sezione commenti -->


      </div>

    </div>
  </div>
</template>

<script>
export default {
  name : 'BloccoPost',
  props:{
    posts: Object,
  },
  data() {
    return {
      nCommenti : 3,
      i : 3,
    }
  },

  methods:{

    loadMore(posts){
      this.nCommenti = posts.comments.length;
    },

    loadLess(){
      this.nCommenti =  this.i ;
    },

  }
};

</script>

<style lang="scss" scoped>
@import '../assets/style/mixin';

  .box-post{
      margin-top: 50px;
      margin-bottom: 50px;
      border: 1px solid rgb(192, 192, 192);
      background-color: white;
      .user-post{
        padding: 20px 0 10px 0;
        flex-direction:column;
        margin-bottom: 50px;
        
        .header-post{
          padding-left: 10px;
          margin-bottom:10px;
          .icona{  
            img{
              border: 2px solid rgb(156, 11, 144);
              padding: 2px;
              width: 55px;
              height: 55px;
              border-radius: 50%;
            }
          }
          .testo{
            margin: 10px 0 0 10px;
            p{
              margin-top: -10px;
              font-size: 0.8em;
              color: rgb(199, 199, 199);
            }
          }
        }
        .post{
          
          .p-img img{
            width: 100%;
          }
          .p-test{
            margin: 20px 0 20px 0px;

            .fa-heart,
            .fa-comment{
              font-size: 1.5em;
              margin-right: 10px;
              color: #b100f7; 
            }
          }
          .like{
            p{
              margin: 0px 0 0 10px;
            }
            
          }
          .user{
            margin: 0px 0 10px 20px;
            img{
              width: 20px;
              height: 20px;
              border-radius: 50%;
            }
          }
          h5{
            margin-left: 20px;
          }
          .commenti{
            span{
            margin-left: 10px;
            font-size: 0.8em;
            }
          }
          .btn{
            margin-left: 20px;        
            outline: none;
            color: rgb(172, 172, 172);
            font-size: 1.2em;
            cursor: pointer;
          }
        }       
      }
    }
</style>