<template>
  <div class="about">
      <b-container>
          <b-row class="mt-5 middle">
              <b-col class="mt-5 img_middle">
                  <div class="images" data-aos="fade-right" data-aos-delay="500" data-aos-duration="1500">
                       <img src="../static/about_img.png" class="first_img" alt="" >
                  </div>
                  <img src="../static/about_img_2.png" class="second_img" alt="" data-aos="zoom-in" data-aos-delay="600" data-aos-duration="1500">
              </b-col>
              <b-col class="mt-5">
                  <strong class="text-uppercase about_company">get to know about our company</strong>
                  <h3 class="text-capitalize"> digital-solutions company</h3>
                  <p class="text_1">SM Digital Tech helps smaller , medium-sized & Enterprise businesses
                                    grow bigger by managing their business in more professional way.
                                    All without the need of any technical knowledge.
                  </p>
                  <b-row>
                      <b-col cols="1"><i class="fa-solid fa-handshake" data-aos="fade-down" data-aos-delay="700" data-aos-duration="2000"></i></b-col>
                      <b-col>
                          <h4 class="text-capitalize our">our <span>mission</span></h4>
                          <p class="text_1">At SM Digital Tech our mission is to help SME's grow online, 
                                have their own web presence without worrying about technology.
                          </p>

                      </b-col>
                  </b-row>
              </b-col>
          </b-row>
      </b-container>

  </div>
</template>

<script>
export default {
    name:'about_vue',

}
</script>

<style scoped>
    .first_img{
        position: relative;
        border-radius: 10px;
    }
    .second_img{
        width: 30%;
        position: absolute;
        top: 50%;
        left: 50%;
        border-radius: 10px;
        background: #fff;
        box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
    }
    .about_company{
        font-size: 20px;
        color: #1c233f;
    }
    .our{
        color: #1c233f;
        font-weight: 600;
    }
    h3{
        margin: 12px 0px;
        color: #f7bc08;
    }
    .fa-handshake{
        font-size: 30px;
    }
    span{
        color: #f7bc08;
    }
    .icon_nav{
        max-width: 0% !important;
    }
    @media screen and (max-width:1024px){
        .first_img{
            width: 75%;
        }
        .second_img{
            width: 40%;
        }
        .fa-handshake{
            font-size: 24px;
        }
    }
    @media screen and (max-width:992px){
        .middle{
            flex-direction: column;
        }
        .img_middle{
            display: flex;
            justify-content: center;
        }
        .first_img{
            position: relative;
            top: -30px;
        }
        .second_img{
            width: 25%;
        }
    }
    @media screen and (max-width:600px){
        h3{
            font-size: 23px;
        }
        .our{
            font-size: 20px;
        }
    }
    @media screen and (max-width:480px){
        .images{
            display: flex;
            justify-content: center;
            position: relative;
            top: -27px;
        }
    }
    @media screen and (max-width:375px){
        .our{
            font-size: 18px;
        }
        .fa-handshake{
            font-size: 20px;
        }
        .about_company{
            font-size: 17px;
        }
        .text_1{
            font-size: 14px;

        }
    }
</style>