<template>
  <v-app id="inspire">
    <navbar></navbar>

    <v-main>
      <home></home>
      <overview></overview>

      <experiance id="Experiance"></experiance>
      <section class="portfolio" id="Portfolio">
        <h4 class="display-2 text-center">If you don't play, you'll never win.</h4>
        <div class="pa-4 text-center portfolio" >- Mark Menson</div>
    
      </section>
      <contact></contact>
    </v-main>
  </v-app>
</template>

<script>
import axios from "axios";
import "../src/css/app.css";
import NavBar from "./components/NavBar.vue";
import OverView from "./components/OverView.vue";
import Home from "@/components/Home.vue";
import Experiance from "@/components/Experiance.vue";
import Contact from "@/components/Contact.vue";

export default {
  name: "App",
  components: {
    navbar: NavBar,
    overview: OverView,
    home: Home,
    experiance: Experiance,
    contact: Contact,
  },
  data: () => ({
    drawer: null,
    items: [
      { title: "HTML", value: 100, color: "light-blue" },
      { title: "CSS", value: 100, color: "deep-orange" },
      { title: "Javascript", value: 70, color: "light-green" },
      { title: "Vuejs", value: 80, color: "blue" },
      { title: "Vuetify", value: 90, color: "black" },
      { title: "PHP", value: 100, color: "red" },
    ],
    ip_address:"",

  }),

    async mounted()
    {
      const response= await axios.get('https://api.ipify.org?format=json').
      then(response=>(this.ip_address = response.data.ip));
      console.log(this.ip_address);
      const res = await axios.post('https://portfolio-ossama.herokuapp.com/api/getIp',{
     ip: this.ip_address ,
   });
      return res + response;

    },

    
  //   async created()
  //   {
           
  //  console.log(res.data);
  //  return res.data; 
  //   }
};
</script>

