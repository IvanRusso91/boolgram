<template>
  <div class="bordo">
    <div class="profile">

      <div class="user">
        <img src="../assets/img/profile.jpg" alt="profile">
      </div>

      <div class="user-name">
        <h5>mariorossi</h5>
        <span>Mario Rossi</span>
      </div>

      <div class="pass">
        <a href="#">Passa a</a>
      </div>
    </div>
      
  </div>
</template>

<script >
export default {
  name: 'BloccoProfilo',
};
</script>

<style lang="scss" scoped>

  @import '../assets/style/mixin';

  .bordo{
    margin-left: 30px;
    .profile{
      display: flex;
      justify-content: space-between;
      margin-top: 15px;
      .user img{
        width: 50px;
        border-radius: 50%;
      }
      .user-name h5{
        margin-bottom: -2px;
      }
      .pass{
        padding-top: 10px;
        a{
          text-decoration: none;
        }
      }
    }
  }

  // MQ

  @media screen and (min-width: 500px) and (max-width: 991px) {
      
      .pass{
        display: none;
      }
      
  }

</style>