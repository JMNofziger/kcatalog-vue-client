<template>
  <div class="about">
    <b-container fluid>
    <b-row>
    <b-col lg="10" offset-lg="1">
    <b-container fluid>
    <b-img left fluid alt="Bush Garden postcard" class="mr-lg-4 mb-4" src="https://s3.amazonaws.com/productimages.goantiques.gemr/194408/667228720_fullsize.jpg"></b-img>
    </b-container>
    <b-container fluid class="about-msg">
        <p>{{msg}}</p>
    </b-container>
    <b-container fluid class="about-msg">
        <p>{{location}}</p>
    </b-container>
    <b-container fluid class="about-msg">
        <p><b-icon icon="link45deg"></b-icon>
        <a href="http://www.bushgarden.net/">Original website</a></p>
    </b-container>
    </b-col>
    </b-row>
    <News />
    </b-container>
  </div>
</template>

<script>
// @ is an alias to /src
import News from '@/components/News.vue';

export default {
  name: 'Home',
  data() {
    return {
      msg: "Bush Garden's lounge has always been a hub of community activity. A regular gathering place - whether it is after work, after leisure, after community events, or for individual milestones (birthdays, weddings, bachelor(ette) parties, retirement, or memorial celebrations), The lounge is a place where people come together to connect and celebrate. It's also a place to unwind or regroup, or just share the company of friends.",
      location: "Historically located at 614 Maynard Avenue South in Seattle - Bush Garden will reopen at Uncle Bob’s Place. Uncle Bob's Place is currently under construction on the corner of South King Street and 8th Avenue South.",
    };
  },
  components: {
    News,
  },
};
</script>
