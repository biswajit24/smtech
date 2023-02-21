<template>
  <div class="box">
      <b-container>
          <b-row class="middle">
              <b-col>
                  <div class="box_area one" >
                    <p class="m-0"><b-avatar class="avtr" size="4rem"><img src="../static/graphic_design.png" class="images"  alt=""></b-avatar></p>
                    <h4 class="text-center text-capitalize">2D promotion</h4>
                  </div>
                </b-col>
              <b-col>
                  <div class="box_area two" >
                    <p class="m-0"><b-avatar class="avtr_2" size="4rem"><img src="../static/social_img.png" class="images"  alt=""></b-avatar> </p>
                    <h4 class="text-center text-capitalize">social media</h4>
                  </div>
              </b-col>
              <b-col>
                  <div class="box_area three" >
                    <p class="m-0"><b-avatar class="avtr" size="4rem"><img src="../static/invoice_img.png" class="images invoice"  alt=""></b-avatar></p>
                    <h4 class="text-center text-capitalize">invoice call</h4>
                  </div>
              </b-col>
              <b-col>
                  <div class="box_area four" >
                    <p class="m-0"><b-avatar class="avtr_2" size="4rem"><img src="../static/map_img.png" class="images"  alt=""></b-avatar></p>
                    <h4 class="text-center text-capitalize">Google Map</h4>
                  </div>
              </b-col>
          </b-row>
      </b-container>
  </div>
</template>

<script>
import scroll from '../plugins/scroll'
export default {
    name:'Box_vue',
    mixins: [scroll]
}
</script>

<style scoped>
    .avtr{
        border-top-left-radius: 0px !important;
        border-top-right-radius: 20px;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;
        background: #ccc;
    }
    .avtr_2 {
        border-top-left-radius: 20px;
        border-top-right-radius: 0px !important;
        background: #ccc;
    }
    .box_area{
        width: 100%;
        height: 130px;
        background: #fff;
        box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.5);
        padding: 10px;
        position: relative;
        top: -30px;
        border-top-right-radius: 20px;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;
        text-align: center;
        transition: 3s ease-in-out;
        display: grid;
        place-items: center;
        overflow: hidden;
    }
    .two, .four{
        border-top-right-radius: 0px;
        border-top-left-radius: 20px;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;
    }
    h4{
      color: #f7bc08;
    }
    .images{
      width: 55%;
    }
    .invoice{
      clip-path: circle(50%);
    }
    .one{
       animation: moveTobottom 5s infinite;
       transition: 0.5s;
    }
    .two{
       animation: moveTotop 4s infinite;
       transition: 0.7s;
    }
    .three{
       animation: moveTobottom 5s infinite;
       transition: 0.5s;
    }
    .four{
       animation: moveTotop 4s infinite;
       transition: 0.7s;
    }
    .box_area::before{
      content: '';
        width: 100%;
        height: 0%;
        position: absolute;
        bottom: 0;
        transition: 0.8s;
        animation-delay: 0.3ms;
        cursor: pointer;
        background: #1c233f;
        color: #fff;
    }
    .box_area:hover::before{
      content: '';
        width: 100%;
        height: 100%;
        transition: 0.8s;
        animation-delay: 0.3ms;
        z-index: -1;
     
    }
    @keyframes moveTobottom {
      0% {
        transform: translateY(0px);
      }
      25% {
        transform: translateY(-20px);
      }
    }
    @keyframes moveTotop {
      0% {
        transform: translateY(0px);
      }
      25% {
        transform: translateY(30px);
      }
    }
    @media screen and (max-width:1140px){
       @keyframes moveTobottom {
      0% {
        transform: translateY(0px);
      }
      25% {
        transform: translateY(20px);
      }
    }

    }
    @media screen and (max-width:992px){
      .middle{
        flex-direction: column;
        width: 60%;
        margin: auto;
      }
      .one , .two, .three,.four{
        animation: 4s;
      }
      .box_area{
        margin-bottom: 10px;
      }
      .box_area:hover{
        transition: 0.8s;
        animation: moveToright 4s ;
        animation-delay: 0.3ms;
      }
       @keyframes moveToright {
      0% {
        transform: translateX(0px)
      }
      25% {
        transform: translateX(40px);
      }
    }
  }
  @media screen and (max-width:768px){
    h4{
      font-size: 20px;
    }
  }
  @media screen and (max-width:600px){
    .one{
      transform: translateX(-25px);
    }
    .two{
      transform: translateX(20px);
    }
    .three{
      transform: translateX(-25px);
    }
    .four{
      transform: translateX(20px);
    }
  }
</style>