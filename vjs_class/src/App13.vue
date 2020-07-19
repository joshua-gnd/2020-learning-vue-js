<template>
  <div>
    <companies v-for="company in companies" :key="company.name" :company="company"></companies>
  </div>
</template>

<script>
import companies from "./components/companies.vue";

export default {
  components: {
    companies
  },

  data() {
    return {
      companies: [
        {
          name: "CEEP",
          address: "St. David, Grenada",
          phone: "444-5501",
          email: "ceep@gmail.com"
        },
        {
          name: "SONOVER",
          address: "St. George, Grenada",
          phone: "414-1111",
          email: "snvr@gmail.com"
        },
        {
          name: "FULLSTACK",
          address: "St. Andrew, Grenada",
          phone: "423-5512",
          email: "flstk@gmail.com"
        }
      ]
    };
  }
};
</script>

<style>
</style>