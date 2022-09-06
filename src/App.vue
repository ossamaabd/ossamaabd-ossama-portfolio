<template>
  <v-app id="inspire">
    

    <v-main>

      <router-view />
    </v-main>
  </v-app>
</template>

<script>



export default {
  name: "App",
  components: {

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
    ip_address: "",
    city: "",
    region: "",
    country_name: "",
    results: [],
  }),

  
  //   async created()
  //   {

  //  console.log(res.data);
  //  return res.data;
  //   }
};
</script>
