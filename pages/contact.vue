<template>
<div class="contact">
    <Navbarportion />
    <div class="contact_banner">
        <b-container>
            <h2 class="text-capitalize" data-aos="zoom-in" data-aos-delay="600" data-aos-duration="1500">contact <span>us</span></h2>
            <div class="text-capitalize text_1">
                <div class="demo_line" data-aos="fade-left" data-aos-delay="600" data-aos-duration="2000"></div>
            </div>
        </b-container>
    </div>
    <b-container>
        <b-row class="mt-5 img_align">
            <b-col>
                <div class="left_contact" data-aos="fade-down" data-aos-delay="600" data-aos-duration="1500">
                    <b-button class="d-flex w-100 adjust">
                        <b-avatar class="address"> <i class="fa-solid fa-location-crosshairs"></i></b-avatar>
                        <p class="text_2 text-capitalize"><a href="https://goo.gl/maps/NfV4U5b1qMwvBMcp6" target="_blank">tribeni market, garia, kolkata</a></p>
                    </b-button>

                </div>
                <div class="left_contact" data-aos="fade-up" data-aos-delay="600" data-aos-duration="1500">
                    <b-button class="d-flex w-100 adjust">
                        <b-avatar class="address"><i class="fa-solid fa-phone"></i></b-avatar>
                        <p class="text_2"><a href="tel:9111170884">9111170884 /</a> <a href="tel:7000375881">7000375881</a></p>
                    </b-button>
                </div>
                <div class="left_contact" data-aos="fade-up" data-aos-delay="600" data-aos-duration="2000">
                    <b-button class="d-flex w-100 adjust">
                        <b-avatar class="address"><i class="fa-solid fa-envelope-circle-check"></i></b-avatar>
                        <p class="text_2"><a href="mailto:shantanu@smdigitaltech.com">shantanu@smdigitaltech.com</a></p>
                    </b-button>
                </div>
                <div class="left_contact" data-aos="fade-up" data-aos-delay="600" data-aos-duration="2000">
                    <b-button class="d-flex w-100 adjust">
                        <b-avatar class="address"><i class="fa-solid fa-business-time"></i></b-avatar>
                        <p class="text_2 text-capitalize"><a href="https://www.google.co.in/maps/place/SM+Digital+Tech/@22.463178,88.3773504,17z/data=!3m1!4b1!4m5!3m4!1s0x3a0271bca7c11ef9:0x3c0cd974537d4109!8m2!3d22.463178!4d88.3795444?hl=en" target="_blank">office hours 10:00 - 6:00 PM</a></p>
                    </b-button>
                </div>
            </b-col>
            <b-col  class="right_img text-center">
                <b-form ref="form" @submit="sendMessage" action="https://sheetdb.io/api/v1/3639vqp14euj0" method="post">
                    <b-row class="devide">
                        <b-col class="my-2">
                            <div class="inside">
                                <input type="text"  class="name" maxlength="50" v-model="name" name="Fullname"  required>
                                <label class="inside_write">Enter Your Name</label>
                            </div> 
                        </b-col>
                        <b-col class="my-2">
                            <div class="inside">
                                <input type="email" class="email"  v-model="email" name="Email" required>
                                <label class="inside_write">Email</label>
                            </div>
                        </b-col>
                    </b-row>
                    <div class="my-2 inside">
                        <input type="text" class="subject" v-model="subject" name="Subject" required>
                        <label class="inside_write">Subject</label>
                    </div>
                    <div class="my-3 inside">
                        <textarea  class="textarea" v-model="message" name="Message" placeholder="Enter Message..." rows="8"></textarea>
                    </div>

                    <b-button class="send text-uppercase" type="submit">Send Message</b-button>
                </b-form>

            </b-col>
        </b-row>
    </b-container>

    <div class="map">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3687.0919684674013!2d88.3795444!3d22.463178!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3a0271a17947327f%3A0x57250cb2d3be2d3c!2sTribeni%20Apartment%2C%20Garia%20Main%20Rd%2C%20Purbapara%2C%20Kamdahari%2C%20Kolkata%2C%20West%20Bengal%20700084!5e0!3m2!1sen!2sin!4v1656483541756!5m2!1sen!2sin" width="100%" height="600" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>
    <Footerportion />
</div>
</template>

<script>
import emailjs from '@emailjs/browser'
import axios from 'axios'
export default {
    name: 'Contact_vue',
      data() {
        return {
            name: '',
            email:'',
            subject:'',
            message: '',
        }
    },
    methods: {
         sendMessage(e, variant= null) {
            e.preventDefault()
            axios.post('https://sheetdb.io/api/v1/3639vqp14euj0', {
                    Fullname: this.name,
                    Email: this.email,
                    Subject: this.subject,
                    Message: this.message,
                })
                .then((res) => console.log(res))
                .catch((res) => console.log(res))
            if (this.name && this.email || this.subject || this.message) {
                swal("Thank You!", "Data Submitted Successful!", "success");
            } 
            this.name = ''
            this.email = ''
            this.subject = ''
            this.message = ''
              emailjs.sendForm('service_tech2', 'template_hwys1i6', this.$refs.form, 'Vll_UBQN9DUzACQ1U')
        .then((result) => {
            console.log('SUCCESS!', result.text);
        }, (error) => {
            console.log('FAILED...', error.text);
        });
            
        },
     
    },

}
</script>

<style scoped>
.img_align{
  width: 100%;
  height: auto;
  padding: 15px 10px;
  background: #fff;
  box-shadow: 0px 0px 3px rgba(0, 0, 0, 0.5);
  border-radius: 10px;
}
.contact_banner {
    background: url("../static/contactpage_img.jpg") no-repeat center center fixed; 
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    width: 100% !important;
    height: 450px;
    display: flex;
    align-items: center;
    position: relative;
    clip-path: polygon(100% 0, 100% 67%, 93% 97%, 7% 97%, 0 100%, 0% 0%);
}

.contact_banner::before {
    content: '';
    position: absolute;
    top: 0;
    width: 100%;
    height: 100%;
    background: #1c233f;
    opacity: 0.6;
}

span {
    color: #f7bc08;
}

.text_1 {
    width: 80px;
    height: 5px;
    background: #fff;
    position: relative;
    border-radius: 10px;
}

.demo_line {
    position: absolute;
    top: -3px;
    left: 10%;
    width: 12px;
    height: 12px;
    border-radius: 40px;
    background: #f7bc08;
}

h2 {
    position: relative;
    color: #fff;
    font-size: 40px;
}

.left_contact {
    background: #1c233f;
    width: 100%;
    text-align: center;
    padding: 15px 12px;
    margin-bottom: 10px;
    display: flex;
}

.left_contact:hover {
    cursor: pointer;
}
.address {
    width: 50px;
    height: 50px;
    margin: 0px 15px;
}

.text_2 {
    margin: 10px 15px 0px 0px;
}

.text_2>a {
    color: #fff;
    text-decoration: none;
    font-weight: 700;
}

.text_2>a:hover {
    color: #f7bc08;
}

.icons {
    font-size: 19px;
    color: #1c233f;
}

.map {
    width: 100%;
    margin-top: 20px;
    position: relative;
    top: 5px;
}

.adjust{
  background: #1c233f;
  box-shadow: 0px 0px 3px rgba(255, 255, 255, 0.5);
  border:none;
}
.adjust:hover{
  background: #ccc;
}
.adjust:hover .text_2>a{
  color: #1a1a1a;
}
.adjust:hover .address{
  background: #1a1a1a;
}
.adjust:hover .fa-location-crosshairs {
  color: #fff;
}
.adjust:hover .fa-phone{
  color: #fff;
}
.adjust:hover  .fa-envelope-circle-check {
  color: #fff;
}
.adjust:hover  .fa-business-time{
  color: #fff;
}
input, textarea{
    padding: 10px 10px;
    width: 100%;
    margin: auto;
    border: 1px solid #929292;
    border-radius: 5px;
    background: transparent;
    outline: none;
    color: #1c233f;
    font-weight: 500;
}
.inside{
    position: relative;
}
.inside>.inside_write {
    position: absolute;
    left: 11px;
    top: 20%;
}
.inside input:valid,
.inside input:focus {
    border: 1px solid #f6bb00;
    border-top: 0;
}
.inside input:valid~.inside_write,
.inside input:focus~.inside_write {
    color: #1c233f;
    transform: translateX(-3px) translateY(-26px);
    transition: 0.3s;
    border-radius: 2px;
    padding: 0px 2px;
}
.inside textarea:focus {
    border: 1px solid #f6bb00;
    border-top: 0;
}

.send{
    background: #1c233f;
    position: relative;
    z-index: 1;
    padding: 9px 15px;
    overflow: hidden;
}
.send::before{
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    width: 0%;
    height: 100%;
    background: #f7bc08;
    transition: all 0.5s;
    
}
.send:hover::before{
    width: 100%;
    height: 100%;
    background: #f7bc08;
    transition: all 0.5s;
    z-index: -1;
}
.send:hover{
    color: #1c233f;
}

@media screen and (max-width:992px) {
    .img_align {
        flex-direction: column;
        margin: auto;
    }
    .left_contact {
        width: 100%;
    }

    .img_align {
        align-items: center;
    }

    h2 {
        color: #f7bc08;
    }

    .text_1 {
        background: #ccc;
    }
    
}

@media screen and (max-width:768px) {
    .left_contact {
        margin: 10px auto;
    }
    .devide{
        flex-direction: column;
    }
}

@media screen and (max-width:568px) {
    h2 {
        font-size: 35px;
    }
    .demo_line {
        width: 10px;
        height: 10px;
    }
}

@media screen and (max-width:480px) {
    .text_2 {
        font-size: 14px;
        margin: 10px auto ;
    }
    .adjust{
        flex-direction: column;
    }
    .address{
        width: 40px;
        height: 40px;
        margin:auto;
    }
}

</style>