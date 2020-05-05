<template>
  <div class="home">
    <Header />
    <img center fluid alt="Bush Garden logo" class="ml-auto" src="../assets/logo.jpg">
    <b-col xs="10" class="ml-auto">
      <br/>
      <CatalogContainer />
    </b-col>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue';
import CatalogContainer from '@/components/CatalogContainer.vue';

export default {
  name: 'Home',
  data() {
    return {
      msg: '',
    };
  },
  components: {
    Header,
    CatalogContainer,
  },
};
</script>
