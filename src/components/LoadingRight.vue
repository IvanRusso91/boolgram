<template>
  <div class="container-fluid box-right">
      <div  class=" box-profilo">
        <div class="bordo">
          <section class="profile d-flex">

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
          </section>
      
        </div>

        <div class="suggeriti d-flex">
          <h6 class="sug-left">Suggeriti per te</h6>
          <h6>Mostra tutti</h6>
        </div>

        <section class="user d-flex">
          <div class="icona">
            <div class="testo">
              <div class="bt" ></div>
              <div class="bt2" ></div>
            </div>
          </div>
          
          <div class="icona">
            <div class="testo">
              <div class="bt" ></div>
              <div class="bt2" ></div>
            </div>
          </div>

          <div class="icona">
            <div class="testo">
              <div class="bt" ></div>
              <div class="bt2" ></div>
            </div>
          </div>

          <div class="icona">
            <div class="testo">
              <div class="bt" ></div>
              <div class="bt2" ></div>
            </div>
          </div>

          <div class="icona">
            <div class="testo">
              <div class="bt" ></div>
              <div class="bt2" ></div>
            </div>
          </div>

          <div class="icona">
            <div class="testo">
              <div class="bt" ></div>
              <div class="bt2" ></div>
            </div>
          </div>

          <div class="icona">
            <div class="testo">
              <div class="bt" ></div>
              <div class="bt2" ></div>
            </div>
          </div>
          
        </section>
        
        <footer>
            <span><i class="fa-regular fa-copyright"></i> 2022 instagram from facebook</span>
          </footer>
      </div>
    </div>
</template>

<script>
export default {
  name: 'LoadingRight',
}
</script>

<style lang="scss" scoped>

  @import '../assets/style/mixin';

  .box-right{
    margin-left: 30px;
    .box-profilo{
      width: 430px;
      margin-top: 50px;
      .suggeriti{
        justify-content: space-between;
        margin: 80px 0  20px 0px;
        .sug-left{
          color: rgb(192, 192, 192);
        }      
      }
      .bordo{
        
        .profile{
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
      .user{
        flex-direction: column;
        .icona{ 
          margin-bottom: 20px; 
          @include user;    
        }
        .testo{
           margin: 10px 0 0 60px;  
          .bt{
            width: 100px;
            height: 10px;
            background: linear-gradient(to right,rgb(173, 173, 173), rgb(247, 247, 247));
          }
          .bt2{
            width: 50px;
            height: 10px;
            margin-top: 5px;
            background: linear-gradient(to left,rgb(173, 173, 173), rgb(247, 247, 247));
          }
        }  
      }
      footer{
        span{
          text-transform: uppercase;
          font-size: 0.7em;
          color: rgb(192, 192, 192);
        }
      } 
    }
  }

  
</style>