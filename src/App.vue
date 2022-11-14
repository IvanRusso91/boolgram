<template>
  <div id="app">

    <div class="container-fluid box">

      <!-- contenitore della nav -->
      <div class="container box-head d-flex">
        <!-- Logo -->
        <div class="logo">
          <img src="./assets/img/logo.png" alt="logo">
        </div>
        <!-- /Logo -->


        <div class="soarch">
          <input type="text" placeholder="Soarch...">
        </div>

        <!-- User a destra conrispettive icone -->
        <div class="user">
          <ul>
            <li><a href="#"><i class="fa-regular fa-heart"></i></a></li>
            <li><a href="#"><i class="fa-solid fa-house"></i></a></li>
            <li>
              <a class="utente" href="#">
                <img src="./assets/img/profile.jpg" alt="profile">
              </a>
            </li>
          </ul>
        </div>
        <!-- User a destra conrispettive icone -->

      </div>
      <!-- Fine contenitore della nav -->
    </div>

    <!-- Main -->
    <div class="container-fluid box-main">
      <div class="container">
        <MainComp />     
      </div>
    </div>
    <!-- /Main -->

    
    
  </div>
</template>

<script>

import MainComp from '@/components/MainComp';

export default {
  name: 'App',
  components: {
    MainComp,
  }
}
</script>

<style lang="scss">

@import './assets/style/_general.scss';
@import './assets/style/_mixin.scss';

.box{
  border-bottom: 1px solid rgb(192, 192, 192);
  .box-head{
    justify-content: space-between;
    padding: 20px 0 0 0 ;
    .logo img{
      margin: 0 20px 0 20px;
      width: 100px;
    }
    .soarch{
      justify-content: center;
      align-content: center;
      input{
        text-align: center;
        width: 250px;
      }
    }
    .user{
      ul {
        @include  center;
        li{
          margin-right: 20px;
          a i{
            color: black;
          }
          a img{
            width: 40px;
            border-radius: 50%;
          }
        }
      }
    }
  }
}

.box-main{
  background-color: rgb(241, 241, 241);
}

</style>
