<template>
  <div class="footer_portion">
      <b-container>
          <b-row class="pt-5 align">
              <b-col cols="5 content_align">
                  <p  class="heading"><img src="../static/logo_img2.png" class="logo_img" alt="" data-aos="fade-up" data-aos-anchor-placement="bottom-bottom" data-aos-duration="2000"></p>
                  <p  class="text_1">At SM Digital Tech our mission is to help SME's grow online, 
                                have their own web presence without worrying about technology.</p>
                  <div class="footer_icon">
                      <b-avatar class="icon" data-aos="fade-right" data-aos-anchor-placement="bottom-bottom"  data-aos-duration="2000" ><a href="https://www.facebook.com/smdigitaltech27" target="_blank"><i class="fa-brands fa-facebook"></i></a></b-avatar>
                      <b-avatar class="icon" data-aos="fade-up" data-aos-anchor-placement="bottom-bottom"  data-aos-duration="2000"><a href="https://www.instagram.com/smdigitaltech27/" target="_blank"><i class="fa-brands fa-instagram"></i></a></b-avatar>
                      <b-avatar class="icon" data-aos="fade-left" data-aos-anchor-placement="bottom-bottom"  data-aos-duration="2000"><a href="https://www.behance.net/smdigitaltech1" target="_blank"><i class="fa-brands fa-behance"></i></a></b-avatar>
                  </div>
              </b-col>
              <b-col>
                  <p class="heading text-uppercase">quick links</p>
                  <ul class="link_portion">
                      <li @click="Homepage">home</li>
                      <li @click="Aboutpage">about</li>
                      <li @click="Servicepage">services</li>
                      <li @click="Contactpage">contact</li>
                  </ul>
              </b-col>
              <b-col>
                  <p class="heading text-uppercase">contact us</p>
                  <ul class="address_portion">
                    <li class="text-capitalize"><a href="https://goo.gl/maps/NfV4U5b1qMwvBMcp6" target="_blank">
                        <b-row>
                            <b-col cols="2" class="middle"><i class="fa-solid fa-location-crosshairs"></i></b-col> 
                            <b-col class="p-0 content_text">garia, kolkata, india</b-col>
                        </b-row> 
                    </a></li>
                    <li><a href="tel:91111-70884,7000375881"> 
                        <b-row>
                            <b-col cols="2" class="middle"><i class="fa-solid fa-phone"></i></b-col>
                            <b-col class="p-0 content_text"><a href="tel:91111-70884">+91 91111-70884</a>/<a href="tel:7000375881">70003-75881</a></b-col>
                        </b-row>
                    </a></li>
                    <li><a href="mailto:shantanu@smdigitaltech.com">
                        <b-row>
                            <b-col cols="2" class="middle"><i class="fa-solid fa-envelope-circle-check"></i></b-col>
                            <b-col class="p-0 content_text"><a href="mailto:shantanu@smdigitaltech.com">shantanu@smdigitaltech.com</a></b-col>
                        </b-row> 
                    </a></li>
                    <li class="text-capitalize"><a href=""> 
                        <b-row>
                            <b-col cols="2" class="middle"><i class="fa-solid fa-business-time"></i></b-col>
                            <b-col class="p-0 content_text"><a href="https://www.google.co.in/maps/place/SM+Digital+Tech/@22.463178,88.3773504,17z/data=!3m1!4b1!4m5!3m4!1s0x3a0271bca7c11ef9:0x3c0cd974537d4109!8m2!3d22.463178!4d88.3795444?hl=en" target="_blank">office hours: 10:00 - 6:00 PM</a> </b-col>
                        </b-row>
                    </a></li>
                  </ul>
              </b-col>
          </b-row>
          
      </b-container>
        <div class="footer_last">
            <p class="text_footer text-center text-capitalize">copyright ©2023- <span><a href="https://www.google.co.in/maps/place/SM+Digital+Tech/@22.463178,88.3773504,17z/data=!3m1!4b1!4m5!3m4!1s0x3a0271bca7c11ef9:0x3c0cd974537d4109!8m2!3d22.463178!4d88.3795444?hl=en" target="_blank">smdigitaltech</a></span> - all right reserved.</p>
        </div>
        <!--<img src="https://chart.apis.google.com/chart?cht=qr&chs=250x250&chl=https://www.smdigitaltech.com/">-->

  </div>
</template>

<script>
export default {
    name:'Footer_vue',

    methods:{
        Aboutpage() {
            this.$router.push('/about');
        },
        Homepage() {
            this.$router.push('/');
        },
        Servicepage() {
            this.$router.push('/service');
        },
        Contactpage() {
            this.$router.push('/contact');
        }
    }

}
</script>

<style scoped>
.footer_portion{
    background: #1c233f;
}
.icon{
    width: 40px;
    height: 40px;
}
ul{
    padding: 0px;
}
.link_portion > li{
    text-transform: capitalize;
    line-height: 40px;
    color: #ccc;
    list-style: none;
    cursor: pointer;
}
.address_portion > li{
     list-style: none;
}
.address_portion > li> a{
    line-height: 40px;
    color: #ccc;
    text-decoration: none;
}
.link_portion > li:hover,.address_portion > li> a:hover{
    color: #f7bc08;
}
.heading{
     color: #f7bc08;
     font-weight: 700;
}
.text_1{
    color: #ccc;
}

.footer_last{
    width: 100%;
    height: 50px;
    background: #1c233f;
    padding: 10px 0px;
    align-items: center;
    justify-content: center;
    border-top: 1px solid #575758;
}
.text_footer{
    color: #ccc;
}
span > a{
    color: #f7bc08;
    text-transform: lowercase;
    text-decoration: none;
}
.middle{
    text-align: center;
    margin: 0px -6px;
}
.content_text > a{
    color: #ccc;
    text-decoration: none;
}
.content_text > a:hover{
    color: #f7bc08;
}

@media screen and (max-width:992px){
    .align{
        flex-direction: column;
    }
    .middle{
        text-align: center;
        max-width: 10%;
        position: relative;
        left: -6px;
    }
    .heading{
        margin-top: 25px;
    }
    .content_align{
        max-width: 100%;
    }
}
@media screen and (max-width:768px){
    .middle{
        left: 0;
    } 
    .logo_img{
        width: 37%;
    }
}
@media screen and (max-width:568px){
    .logo_img{
        width: 30%;
    }
}
 @media screen and (max-width:480px){
    .middle{
        max-width: 14%;
    }
    .text_footer{
        font-size: 13px;
    }
 }
 @media screen and (max-width:360px){
    .logo_img{
        width: 40%;
    }
    .content_text{
      padding: 0px 15px !important;
    }
    .text_footer{
        font-size: 13px;
    }
    h2{
        font-size: 32px;
    }
  }
</style>