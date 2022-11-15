<template>
  <div class="box d-flex">
    <div class="box-left d-flex">

      <!-- Storie -->
      <div class="box-storie">

        <!-- loading.. -->
        <dir class="loading">
          <img src="../assets/img/spinner.gif" alt="spinner">
        </dir>
        <!-- /loading.. -->
          
        <div class="bs d-flex">
          <section class="story-users d-flex">
            <div class="icona"></div>
            <div class="icona"></div>
            <div class="icona"></div>
            <div class="icona"></div>
            <div class="icona"></div>
            <div class="icona"></div>
            <div class="icona"></div>
            <div class="icona"></div>
          </section>
        </div>

      </div>
      <!-- /Storie -->


      <!-- Post -->
      <div class="box-post ">   
        <div class="user-post">
          <div class="header-post d-flex">

            <section class="icona">
              <div class="user-icona"></div>
            </section>

            <section class="testo">
              <div class="bt"></div>
              <div class="bt2"></div>
            </section>

          </div>
        </div>
      </div>
      <!-- /Post -->
    </div>
  </div>
</template>

<script>
export default {
  nome: 'LoadingComp',
}
</script>

<style lang="scss" scoped>

@import '../assets/style/mixin';

.box{
  .box-left{
    width: 780px;
    flex-direction: column;
    .box-storie{
      border: 1px solid rgb(192, 192, 192);
      margin-top: -20px;
      background-color: white;
      .bs{
        overflow-x: hidden;
        padding: 20px 0 20px 20px;
        .story-users{
          margin-right: 35px;
          text-align: center;
          .icona{
            margin-right: 20px;
            @include user
          }
        }
      }
      .loading{
        text-align: center;
        margin-top: 20px;
      }   
    }
    .box-post{
      height: 500px;
      margin-top: 50px;
      border: 1px solid rgb(192, 192, 192);
      background: linear-gradient(to bottom,
      rgb(255, 255, 255) 15vh,rgb(219, 219, 212) 0vh);
      .user-post{
        padding: 20px 0 0px 0;
        .header-post{
          padding-left: 10px;
          .icona{  
            .user-icona{
             @include user
            }
          }
          .testo{
            margin: 10px 0 0 10px;
            .bt{
              width: 150px;
              height: 10px;
              background: linear-gradient(to right,rgb(226, 225, 225), rgb(247, 247, 247));
            }
            .bt2{
              width: 100px;
              height: 10px;
              margin-top: 5px;
              background: linear-gradient(to left,rgb(226, 225, 225), rgb(247, 247, 247));
            }
          }
        }  
      }
    }    
  } 
}

// MQ

  @media screen and (min-width:1200px) and (max-width: 1399px) {

      .box{
        .box-left{
          width: 680px;
        }
      }
    
  }

   @media screen and (min-width:992px) and (max-width: 1199px) {

    .box{
      .box-left{
        width: 580px;
      }
    }
  }

  @media screen and (min-width:768px) and (max-width: 991px) {

    .box{
      .box-left{
        width: 420px;
      }
    }
  }

  @media screen and (min-width:768px) and (max-width: 991px) {

    .box{
      .box-left{
        width: 420px;
      }
    }
  }

  @media screen and (min-width:500px) and (max-width: 767px) {

    .box{
      .box-left{
        width: 280px;
      }
    }
  }

</style>