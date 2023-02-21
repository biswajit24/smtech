<template>
<div class="header">
    <div class="header_nav">
        <b-container>
            <b-row class="between">
                <b-col class="adjust">
                    <img src="../static/logo_img2.png" class="logo" alt="" data-aos="fade-down" data-aos-delay="500" data-aos-duration="1000">
                    <button class="button_icon">
    
                        <i class="fa-solid fa-bars-staggered" v-if="show" aria-hidden="true" @click="Navchange"></i>
                        <i class="fa fa-times" v-if="hide" @click="HiddenClick" aria-hidden="true"></i>
                    </button>
                </b-col>
                <b-col class="p-0 end">
                    <nav class="shift" :class="change">
                        <ul>
                            <li><a @click="Homepage" class="active">
                                    <b-row class="nav_align">
                                        <div class="demo">
                                            <i class="fa-solid fa-house-user"></i>
                                            home
                                        </div>
                                    </b-row>
                                </a></li>
                            <li><a @click="Aboutpage">
                                    <b-row class="nav_align">
                                        <div class="demo">
                                            <i class="fa-solid fa-circle-info"></i>
                                            About
                                        </div>
                                    </b-row>
                                </a></li>
                            <li id="popover-target-1"><a>
                                    <b-row class="nav_align">
                                        <div class="demo">
                                            <i class="fa-sharp fa-solid fa-gears"></i>
                                            <span @click="Servicepage"> service </span>
                                        </div>
                                    </b-row>
                                </a></li>
                            <li><a @click="Contactpage">
                                    <b-row class="nav_align">
                                        <div class="demo">
                                           <i class="fa-solid fa-phone"></i>
                                            contact
                                        </div>
                                    </b-row>
                                </a></li>

                        </ul>
                        <b-popover target="popover-target-1" id="drop" triggers="hover" placement="bottomtop">
                            <li class="list" @click="subpage">web design & seo</li>
                            <li class="list" @click="subpage_2">graphic design</li>
                            <li class="list">mobile app</li>
                            <li class="list">branding marketing</li>
                            <li class="list">bulk sms</li>
                            <li class="list">3d promotion</li>
                            <li class="list">social media</li>
                            <li class="list">invoice call</li>
                            <li class="list google_map">google map</li>
                        </b-popover>
                    </nav>

                </b-col>

            </b-row>

        </b-container>

    </div>
    <!--<div class="scrollto_top" @click="Scrolltop"><a href=""><i class="fa fa-arrow-up" aria-hidden="true"></i></a></div>-->
</div>
</template>

<script>
export default {
    name: 'Nav_vue',
    data() {
        return {
            show: true,
            hide: false,
            serve: false,
        }
    },
    methods: {
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
        },
        subpage(){
            this.$router.push('/services/webdesign_seo')
        },
        subpage_2(){
            this.$router.push('/services/graphic_design')
        },
        
        Navchange() {
            this.show = !this.show;
            this.hide = !this.hide;
            this.change = 'navbar';
        },
        HiddenClick() {
            this.change = 'shift';
            this.show = !this.show;
            this.hide = !this.hide;
        },
        ServiceDrop() {
            this.chev = !this.chev;
            this.serve = !this.serve;
        }

    }
}
</script>

<style scoped>
.demo {
    padding: 0px 13px;
    color: #fff;
}

html {
    scroll-behavior: smooth;
    transition: 0.5s;
}

.header_nav {
    background: #1c233f;
    margin: auto;
    width: 100%;
    position: fixed;
    top: 0;
    z-index: 10;
    padding: 10px 0px;
}

.between {
    width: 100%;
    justify-content: space-between;
    align-items: center;
}

.end {
    display: flex;
    justify-content: flex-end;
}

nav {
    width: 100%;
    display: flex;
    justify-content: flex-end;
}

nav ul {
    list-style: none;
    text-align: center;
    margin: 0;
    padding: 0px;
}

nav ul li {
    display: inline-block;
}

nav ul li a {
    display: block;
    padding: 7px 18px;
    text-decoration: none;
    color: #f7bc08;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
}

nav ul li .active {
    display: block;
    padding: 7px 19px;
    text-decoration: none;
    color: #1c233f;
    font-weight: 700;
    text-transform: uppercase;
}

nav ul li a,
nav ul li a:after,
nav ul li a:before {
    transition: all .5s;
}

nav ul li a:hover {
    color: #fff;
}

nav.shift ul li a {
    position: relative;
    z-index: 1;
}

nav.shift ul li a:hover {
    color: #1c233f;
    cursor: pointer;
}

nav.shift ul li a:after {
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    margin: auto;
    width: 100%;
    height: 1px;
    content: '.';
    color: transparent;
    border-bottom: 3px solid #f7bc08;
    border-radius: 30px;
    visibility: none;
    opacity: 0;
    z-index: -1;
}

nav.shift ul li a:hover:after {
    opacity: 1;
    visibility: visible;
    height: 100%;
}

.list {
    list-style: none;
    text-transform: capitalize;
    line-height: 35px;
    padding: 0px 15px;
    border-bottom: 0.25px solid #ddd;
    background: #1c233f;
    color: #fff;
}

.list:hover {
    width: 100%;
    transition: 0.5s;
    transform: translateX(8px);
    color: #f7bc08;
    cursor: pointer;
}

.google_map {
    border: none;
}

#drop {
    top: 7px !important;
}

.scrollto_top {
    position: fixed;
    top: 90%;
    left: 95%;
    right: 0;
    width: 50px;
    height: 50px;
    background: #f7bc08;
    border-radius: 50%;
    z-index: 10;
    display: grid;
    place-items: center;
    cursor: pointer;
}

.fa-arrow-up {
    color: #1c233f;
}

.fa-bars,
.button_icon {
    display: none;
}

@media screen and (max-width:1200px) {
    .logo {
        width: 37%;
    }

    nav ul li .active,
    nav ul li a {
        padding: 0px 3px;
    }

    nav.shift ul li a:after {
        top: 12px;
    }

    .demo {
        padding: 0px 19px;
    }
}

@media screen and (max-width:992px) {
    .nav_align {
        justify-content: center;
    }

    nav.shift ul li a:after {
        top: 0px;
    }

    .fa-house-user,
    .fa-circle-info,
    .fa-gears,
    .fa-phone {
        display: none;
    }

    .fa-chevron-circle-down {
        padding: 0px 6px;
    }

    .adjust {
        display: flex;
        justify-content: space-between;
        padding: 0px;
    }

    .between {
        flex-direction: column;
        margin: 0 !important;
    }

    nav ul li a,
    nav ul li .active {
        padding: 7px 9px;
        font-size: 15px;
        color: #fff !important;
    }

    .fa-bars-staggered {
        display: block;
        font-size: 23px;
    }

    .fa-times {
        font-size: 23px;
        color: #f7bc08;
    }

    .button_icon {
        display: block;
        color: #fff;
        background: transparent;
        border: none !important;
        border-radius: 5px;
        padding: 0px 12px;
    }

    .shift {
        width: 100%;
        background: #1c233f;
        box-shadow: 0px 0px 10px 1px rgba(0, 0, 0, 0.5);
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        position: fixed;
        top: 0;
        right: 0;
        z-index: -1;
        transform: translateY(-100%);
        transition: 0.8s;
        padding: 50px 0px;
    }

    #drop {
        position: fixed !important;
        top: 0% !important;
        transition: 0.6s;

    }
    .navbar {
        width: 100%;
        min-height: 100%;
        transform: translateY(0%);
        transition: 0.9s;
        height: auto !important;
    }

    nav ul li {
        display: block;
        line-height: 37px;
    }

    .logo {
        width: 22%;
    }

    .scrollto_top {
        left: 90%;
        top: 87%;
    }

    .icon_nav {
        padding: 0px;
        max-width: 0 !important;
    }

    .content {
        padding: 0px 20px !important;
    }

    nav.shift ul li a:after {
        background: transparent
    }
}

@media screen and (max-width:600px) {
    .scrollto_top {
        width: 45px;
        height: 45px;
    }
}

@media screen and (max-width:480px) {
    .scrollto_top {
        width: 39px;
        height: 39px;
        left: 88%;
    }

    .logo {
        width: 30%;
    }
    .fa-bars-staggered{
        font-size: 19px;
    }
}

@media screen and (max-width:360px) {
  
    .scrollto_top {
        width: 45px;
        height: 45px;
    }

    .logo {
        width: 30%;
    }

    .scrollto_top {
        width: 40px;
        height: 40px;
    }
}
</style>
