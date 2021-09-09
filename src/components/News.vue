<template>
    <b-container fluid >
    <h5>News</h5>
    <b-col lg="8" offset-lg="2">
        <b-card v-for="item in news" :key="item.article" class="m-lg-3">
            <b-icon icon="link45deg"></b-icon><a :href="item.link">{{ item.article }}</a>
        </b-card>
    </b-col>
    </b-container>
</template>

<script>
export default {
  name: 'News',
  data() {
    return {
      news: [
        {
          article: 'International District’s Long-Running Karaoke Restaurant Will Live on in New Development',
          link: 'https://seattle.eater.com/2019/5/30/18645798/chinatown-international-district-bush-garden-karaoke-restaurant-relocation-four-seas-dynasty-room',
        },
        {
          article: 'Virtual Groundbreaking Of Uncle Bob’s Place Honors Legendary Community Activist',
          link: 'https://southseattleemerald.com/2021/02/28/virtual-groundbreaking-of-uncle-bobs-place-honors-legendary-community-activist/',
        },
        {
          article: 'Edge Developers: Uncle Bob’s Place',
          link: 'https://www.edgedevelopers.net/uncle-bobs-place',
        },
        {
          article: 'Bush Garden plans new home at Uncle Bob’s Place',
          link: 'http://nwasianweekly.com/2019/05/bush-garden-plans-new-home-at-uncle-bobs-place/',
        },
      ],
    };
  },
};
</script>
