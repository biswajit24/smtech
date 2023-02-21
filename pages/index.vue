<template>
<div class="index">
    <Navbarportion />
    <Bannerportion />
    <Boxportion />
    <Aboutportion />
    <div class="mt-5"> <Serviceportion /></div>
    <Contactportion />
    <Footerportion />

    

</div>
</template>

<script>
import Navbarportion from '../components/Navbarportion.vue'
import Bannerportion from '../components/Bannerportion.vue'
import Boxportion from '../components/Boxportion.vue'
import Aboutportion from '../components/Aboutportion.vue'
import Serviceportion from '../components/Serviceportion.vue'
import Contactportion from '../components/Contactportion.vue'
import Footerportion from '../components/Footerportion.vue'



export default {
    name: 'IndexPage',
    components: {
        Navbarportion,
        Bannerportion,
        Boxportion,
        Aboutportion,
        Serviceportion,
        Contactportion,
        Footerportion
    }
}
</script>

<style scoped>
    * {
        font-family: 'Raleway', sans-serif;
    }
 
</style>
