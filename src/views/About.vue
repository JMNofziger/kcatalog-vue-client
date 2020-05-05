<template>
  <div class="about">
    <Header />
    <b-img center fluid alt="Bush Garden postcard" class="ml-auto" src="https://s3.amazonaws.com/productimages.goantiques.gemr/194408/667228720_fullsize.jpg"></b-img>
    <b-container class="about-msg">
      <b-row>
        <p>{{msg}}</p>
      </b-row>
    </b-container>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue';

export default {
  name: 'Home',
  data() {
    return {
      msg: 'Bush Garden is a wonderful bar/community of people that love to sing and enjoy each other’s company. Karaoke is led by a staff member that receives written customer requests and loads them in the KDJ machine in order of request. Customers make requests by searching the paper catalog (compiled in a binder) for a song, then writing the song’s identifier (usually a couple of letters and numbers) and the song name onto a piece of paper, then submitting the piece of paper to the staff member operating the KDJ machine. The binders are sorted alphabetically by artist or by song name. The KDJ takes the customer request papers and queues up the requested song by either looking up the song identifier (digits and numbers) or searching the name which the customer has written down.',
    };
  },
  components: {
    Header,
  },
};
</script>
