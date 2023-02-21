<template>
  <div class="banner">
    
        <b-container>
            <b-row class="left-text">
                <img src="../static/tech_img.png" class="tech_img" alt="">
                <b-col class="left_content">
                    <p class="welcome" data-aos="fade-right" data-aos-delay="500" data-aos-duration="1000">hello to</p>
                    <h2 class="text-capitalize text_1" data-aos="fade-right" data-aos-delay="600" data-aos-duration="1000">the next generation of <br><span> digital</span> ocean</h2>
                    <p class="text_2" data-aos="fade-right" data-aos-delay="700" data-aos-duration="1000">To be the best agency , by empowering businesses with the full potential of internet.
                        One day, all businesses will have the opportunity to come online to drive a
                        new era of development, growth, and productivity along with their brand name.
                    </p>
                    <b-button class="text-capitalize read" data-aos="fade-up" data-aos-delay="700" data-aos-duration="1000">get more</b-button>
                    <b-link href="https://www.youtube.com/embed/HSdKimbng7o" target="_blank" class="link"><b-avatar class="text-capitalize watch" data-aos="fade-up" data-aos-delay="700" data-aos-duration="1000"><i class="fa-regular fa-circle-play"></i></b-avatar> <strong class="text-capitalize">watch video</strong></b-link>  
                   
                </b-col>
                <b-col class="right_img">
                    <div class="circle" data-aos="fade-down" data-aos-delay="500" data-aos-duration="1000"></div>
                    <img src="../static/business_img.png" class="img-1" alt="" data-aos="zoom-in" data-aos-delay="800" data-aos-duration="1000">
                    <div class="circle_2" data-aos="fade-up" data-aos-delay="700" data-aos-duration="1000"></div>
                </b-col>
            </b-row>
        </b-container>
  </div>
</template>

<script>
export default {
    name:'Banner_vue',

}
</script>

<style scoped>
.banner {
    background: #1c233f;
    clip-path: polygon(100% 0, 100% 67%, 93% 97%, 7% 97%, 0 100%, 0% 0%);
    width: 100%;
    height: auto;
    padding: 80px 0px;
    margin-top: 15px;
    position: relative;
}
.banner::before{
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 95%;
    height: 100%;
    background: rgba(247, 188, 8, 0.9);
    clip-path: polygon(52% 0, 100% 100%, 0 100%, 0 0);
    z-index: -1;
}
.banner::after{
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    width: 67%;
    height: 100%;
    background: rgba(28, 35, 63, 0.9);
    clip-path: polygon(100% 0, 100% 100%, 92% 100%, 24% 0);
    z-index: -1;
}
.circle {
    width: 90px;
    height: 90px;
    background: linear-gradient(to bottom, #1c233f, #163a96);
    border-radius: 50%;
    position: absolute;
    top: 2%;
    left: 29%;
    animation: zoom-in-zoom-out 8s infinite;
}
.circle_2 {
    width: 70px;
    height: 70px;
    background: linear-gradient(to bottom, #1c233f, #163a96);
    border-radius: 50%;
    position: absolute;
    top: 25%;
    left: 84%;
    animation: zoom-in-zoom-out 5s infinite;
}
@keyframes zoom-in-zoom-out {
    0% {
        transform: scale(1, 1);
    }
    50% {
        transform: scale(1.2, 1.2);
    }
    100% {
        transform: scale(1, 1);
    }
}
.tech_img{
    position: absolute;
    top: 0;
    left: 0%;
    z-index: -2;
    width: 100%;
}
.img-1 {
    position: relative;
    width: 73%;
    z-index: 1;
}
h2 {
    font-size: 37px;
}
.text_1 {
    color: #fff;
    margin-bottom: 20px;
    font-weight: 700;
    letter-spacing: 2px;
}
.welcome{
    color: #fff;
    text-transform: uppercase;
    letter-spacing: 5px;
}
.text_2 {
    color: #1c233f;
    margin-bottom: 20px;
    line-height: 28px;
}
.left-text {
    align-items: center;
}
.right_img {
    display: flex;
    justify-content: flex-end;
    position: relative;
}
span {
    color: #1c233f;
    font-weight: 800;
}
.read
 {
    background: transparent !important;
    border-radius: 40px !important;
    border: 2px solid #1c233f;
    padding: 9px 20px;
    margin-right: 5px;
    position: relative;
    overflow: hidden;
    color: #1c233f;
    letter-spacing: 2px;
}
.read:hover{
    color: #fff;
}
.read::before{
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    width: 0%;
    height: 100%;
    background: #1c233f;
    transition: all 0.5s;
    z-index: -1;
}
.read:hover::before{
    width: 100%;
    height: 100%;
    background: #1c233f;
    transition: all 0.5s;
}
.link{
    text-decoration: none;
    color: #1c233f;
}
.watch{
    background: transparent;
    border: 2px dashed #1c233f;
    background: transparent;
    transition: all 0.5s;
}
.watch::before{
    content: '';
    position: absolute;
    width: 50px;
    height: 50px;
    background: rgba(255, 255, 255, 0.4);
    border: 3px dashed rgba(255, 255, 255, 0.8);
    border-radius: 50%;
    animation: spin 5000ms linear infinite;
    z-index: -1;
}
@keyframes spin {
    from {
        transform:rotate(0deg);
    }
    to {
        transform:rotate(360deg);
    }
}
.watch:hover{
    background: #1c233f;
    transition: all 0.5s;
}
.watch:hover .fa-circle-play{
    color: #fff;
    transition: all 0.5s;
}
.fa-circle-play{
    color: #1c233f;
}
strong{
    margin: 0px 8px;
}


@media screen and (max-width:1140px){
    .text_1{
        font-size: 35px;
    }
     .tech_img{
        width: 100%;
   }
   .circle{
        left: 29%;
        width: 17%;
        height: 27%;
        object-fit: scale-down;
    }
    .circle_2{
        left: 83%;
        top: 26%;
        width: 13%;
        height: 22%;
        object-fit: scale-down;
    }
}
@media screen and (max-width:992px){
    .text_1{
        font-size: 25px;
    }
    .text_2{
        font-size: 13px;
    }
    .read, .get{
        font-size: 13px;
    }
}
@media screen and (max-width:768px){
    .left-text{
        flex-direction: column;
    }
    .img-1{
        width: 60%;
    }
    .circle{
        left: 22%;
        width: 12%;
        height: 24%;
    }
    .circle_2{
        left: 67%;
        top: 26%;
        width: 10%;
        height: 20%;
    }
    .text_1{
        font-size: 28px;
    }
    .text_2{
        font-size: 17px;
        color: #fff;
    }
     .right_img{
        justify-content: center;
        margin-top: 20px;
        position: relative;
        top: 20px;
   }
    .tech_img{
        width: 100%;
        height: 100%;
   }
}
@media screen and (max-width:600px){
    .text_2, .get,.read{
        font-size: 15px;
        line-height: 25px;
    }
}
@media screen and (max-width:480px){
    .text_1{
        font-size: 27px;
    }
    .text_2{
        font-size: 14px;
        line-height: 23px;
        color: #fff;
    }
    strong{
        color: #fff;
    }
}
@media screen and (max-width:375px){
    .text_1{
        font-size: 22px;
    }
    .read, .get{
        padding: 5px 10px;
        font-size: 12px;
    }
    .watch::before{
        width: 90%;
        height: 90%;
    }
}
@media screen and (max-width:320px){
     .text_1{
        font-size: 18px;
    }
    .call_num, .email {
        font-size: 15px;
    }
}
</style>