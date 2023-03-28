<template>
    <v-app id="home">
        <Navbar />
        <v-container fluid>

        </v-container>
    </v-app>
</template>

<script>
import { defineComponent } from 'vue'
//component
import NavBar from '../components/NavBar'


export default defineComponent({
    name:'HomeView',

    components:{
        NavBar,
    },
})
</script>