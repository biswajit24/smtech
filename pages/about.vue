<template>
<div class="about">
    <Navbarportion />
    <h4 class="text-center text-capitalize text_heading mt-5" data-aos="zoom-in" data-aos-duration="2000">Our solutions begin with startup</h4>
    <div class="line"></div>
    <div class="line_2" data-aos="fade-right" data-aos-duration="2000"></div>
    <b-container>
        <b-row class="mt-5 content_align">
            <b-col class="mt-5 img_align">
                <div class="images">
                    <img src="../static/aboutpage_img3.png" class="first_img" alt="" data-aos="zoom-in" data-aos-duration="2000">
                </div>
            </b-col>
            <b-col class="mt-5">
                <strong class="text-capitalize about_us">about
                    <hr>
                </strong>
                <h3 class="text-uppercase" data-aos="zoom-in" data-aos-duration="2000">company info</h3>
                <p class="text_1" data-aos="fade-down" data-aos-delay="700" data-aos-duration="2000">We want employees to put in long days, respond to their emails at all hours, and willingly donate their off-hours — nights, weekends, vacation — without complaining.
                </p>
                <b-row>
                    <b-col cols="1"></b-col>
                    <b-col>
                        <p class="text_3 text-uppercase" data-aos="fade-up" data-aos-delay="800" data-aos-duration="2000">design & <span class="digital">digital-solutions</span></p>
                    </b-col>
                </b-row>
                <b-button class="text-capitalize read_more" data-aos="fade-up" data-aos-duration="2000">read more</b-button>
            </b-col>
        </b-row>
    </b-container>
    <div class="background mt-2">
        <p class="text-capitalize text_2" data-aos="zoom-in" data-aos-duration="2000">we are located in <span>kolkata</span></p>
    </div>

    <b-container>
        <b-row class="mt-4 content_align">
            <b-col class="mt-5">
                <strong class="text-capitalize about_company" data-aos="fade-left" data-aos-delay="500" data-aos-duration="1000">creative team that gets about
                    <hr>
                </strong>
                <p class="text_1" data-aos="fade-up" data-aos-delay="500" data-aos-duration="1500">
                    Our team of designers and developers are perfectionists who love what they do – we thrive off pushing the boundaries of our clients’ expectations and our own capabilities.
                </p>
                <b-row>
                    <b-col class="start_up">
                            <img src="../static/line_up.png" class="line_img" alt="">
                        <b-button v-b-modal.modal-1 @click="GetTouch" class="text-capitalize get" data-aos="fade-up" data-aos-delay="600" data-aos-duration="2000">get in touch</b-button>
                    </b-col>

                    <!--<b-modal id="modal-1" title="Get In Touch">
                        <b-form ref="form" @submit="sendEmail" action="https://sheetdb.io/api/v1/uafmjtoxir1o0" method="post">
                            <label for="feedback-user" class="text-capitalize">user name</label>
                            <b-form-input type="text" v-model="user" name="user" maxlength="50" :state="validation" id="feedback-user" required></b-form-input>
                            <b-form-invalid-feedback :state="validation">
                                User Name must be 5-50 characters long.
                            </b-form-invalid-feedback>
                            <b-form-valid-feedback :state="validation">
                                Looks Good.
                            </b-form-valid-feedback>
                            <label for="" class="text-capitalize">message</label>
                            <b-textarea type="text" v-model="message" name="message"></b-textarea>
                            <b-button type="submit" class="mt-3 send text-uppercase" variant="success" >send</b-button>
                        </b-form>
                    </b-modal>-->

                </b-row>
            </b-col>
            <b-col class="mt-5 right">
                <div class="image_right" data-aos="zoom-in" data-aos-duration="2000">
                    <img src="../static/aboutpage_img1.png" class="first_img_2" alt="" >
                </div>
            </b-col>
        </b-row>
    </b-container>
    <Footerportion class="mt-4" />
</div>
</template>

<script>
import emailjs from '@emailjs/browser'
import axios from 'axios'

export default {
    name: 'About_vue',
    data() {

        return {
            user: '',
            message: '',
        }
    },
    methods: {
        sendEmail(e, variant = null) {
            e.preventDefault()
            axios.post('https://sheetdb.io/api/v1/uafmjtoxir1o0', {
                    user: this.user,
                    message: this.message,
                })
                .then((res) => console.log(res))
                .catch((res) => console.log(res))
            if (this.user && this.message) {
                swal("Thank You!", "Data Submitted Successful!", "success");
            }
            this.user = ''
            this.message = ''
            emailjs.sendForm('service_id', 'template_id', this.$refs.form, 'public_key')
                .then((result) => {
                    console.log('SUCCESS!', result.text);
                }, (error) => {
                    console.log('FAILED...', error.text);
                });
        },
        GetTouch(){
            this.$router.push('/contact');
        }
    },
    computed: {
        validation() {
            return this.user.length > 5 && this.user.length < 50
        }
    },

}

</script>

<style scoped>
* {
    font-family: 'Raleway', sans-serif;
}

.text_heading {
    position: relative;
    top: 50px;
    font-weight: 700;
}

.line {
    width: 80px;
    height: 4px;
    background: #f7bc08;
    margin: auto;
    border-radius: 10px;
    position: relative;
    top: 51px;
}

.line_2 {
    width: 12px;
    height: 12px;
    background: #1c233f;
    margin: auto;
    border-radius: 50%;
    position: relative;
    top: 43px;
}

.first_img {
    position: relative;
    border-radius: 10px;
    width: 65%;
}

.first_img_2 {
    width: 75%;
}

.about_us {
    font-size: 20px;
    color: #1c233f;
}

.about_company {
    font-size: 20px;
    color: #f7bc08;
}

h3 {
    color: #f7bc08;
    font-size: 25px;
}

h4 {
    color: #1c233f;
    line-height: 36px;
}

.background {
    background: url(../static/background_img.jpg);
    background-size: cover;
    background-repeat: no-repeat;
    box-sizing: border-box;
    width: 100%;
    height: 500px;
    position: relative;
    top: 20px;
    display: grid;
    place-items: center;
    clip-path: polygon(100% 0, 100% 67%, 93% 97%, 7% 97%, 0 100%, 0% 0%);
}

.background::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 50%;
    height: 100%;
    background: #1c233f;
    opacity: 0.6;
    transition: 0.5s;
}

.background:hover::before {
    content: '';
    width: 100%;
    height: 100%;
    background: #1c233f;
    transition: 0.5s;
}

.text_2 {
    font-size: 35px;
    color: #fff;
    font-weight: 500;
    margin: 0px;
    position: relative;
    z-index: 10;
}

span {
    color: #f7bc08;
    font-size: 40px;
    font-weight: 700;
}

.digital {
    color: #1c233f;
    font-size: 22px;
}

.text_3 {
    font-size: 20px;
    color: #1c233f;
    font-weight: 500;
}

.get {
    background: #1c233f;
    border: none;
    transition: all 0.5s;
    position: relative;
    overflow: hidden;
    z-index: 5;
}

.get:hover {
    color: #1c233f;
}

.get::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 0%;
    height: 100%;
    background: #f7bc08;
    transition: all 0.5s;
    color: #1c233f;
    z-index: -1;
}

.get:hover::before {
    width: 100%;
    height: 100%;
    background: #f7bc08;
    transition: all 0.5s;
    color: #1c233f;

}

.right {
    display: flex;
    justify-content: flex-end;
    width: 100%;
}

.image_right {
    text-align: right;
}

.read_more {
    border-radius: 20px;
    padding: 7px 15px;
    background: #1c233f;
    border: none;
    position: relative;
    overflow: hidden;
    z-index: 5;
}

.read_more::before {
    content: '';
    position: absolute;
    width: 0%;
    height: 100%;
    top: 0;
    right: 0;
    color: #fff;
    font-weight: 500;
    transition: all 0.5s;
}

.read_more:hover::before {
    background: #f7bc08;
    width: 100%;
    height: 100%;
    transition: all 0.5s;
    font-weight: 500;
    z-index: -1;
}

.read_more:hover {
    color: #000;
}

.send {
    background: #1c233f;
}
.start_up{
    position: relative;
}
.line_img{
    position: absolute;
    top: 0;
    right: 0;
    left: 45%;
    width: 80%;
    transform: rotate(-5deg);
}
.image_right{
    position: relative;
    width: 320px;
    height: 320px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: all 0.5s;
}
.image_right::before{
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    border: 4px dashed #1c233f;
    animation: spin 10000ms linear infinite;
}
@keyframes spin{
    from{
        transform: rotate(0deg);
    }
    to{
        transform: rotate(360deg);
    }
}

.image_right:hover{
    background: #1c233f;
    transition:all 0.5s;
}

@media screen and (max-width:992px) {
    h3 {
        font-size: 25px;
    }

    .text_1 {
        font-size: 13px;
    }

    h4 {
        font-size: 21px;
    }
}

@media screen and (max-width:768px) {
    .images {
        display: flex;
        justify-content: center;
    }

    .text_3 {
        font-size: 20px;
    }

    .content_align {
        flex-direction: column;
    }

    .first_img_2 {
        animation: moveTobottom 5s infinite;
    }

    @keyframes moveTobottom {
        0% {
            transform: translateY(0%);
        }

        50% {
            transform: translateY(-15%);
        }
    }

    .text_2 {
        font-size: 24px;
    }

    span {
        font-size: 32px;
    }
    .line_img{
        display: none;
    }
    .right{
        justify-content: center;
    }
}

@media screen and (max-width:568px) {
    .about_company {
        font-size: 21px;
    }

    .line_2 {
        width: 9px;
        height: 9px;
        top: 45px;
    }
}

@media screen and (max-width:480px) {
    h3 {
        font-size: 20px;
    }

    .about_company {
        font-size: 18px;
    }

    span {
        display: grid;
    }

    .text_3 {
        font-size: 18px;
    }

    .img_align {
        display: flex;
        justify-content: center;
    }
    .image_right::before{
        width: 0%;
        height: 0%;
    }
}

@media screen and (max-width:360px) {
    .text_3 {
        font-size: 14px;
    }

    .digital {
        font-size: 19px;
    }
}

@media screen and (max-width:320px) {
    .text_heading {
        font-size: 18px;
    }
}
</style>
