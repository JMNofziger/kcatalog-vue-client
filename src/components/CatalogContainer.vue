<template>
  <div class="catalog-container">
    <b-table striped hover :fields=fields :items="items">
      <tr v-for="(song, index) in items" :key="index">
        <td>{{ song.artist}}</td>
        <td>{{ song.song_name }}</td>
      {{items}}
    </tr>
    </b-table>
  </div>
</template>


<script>
export default {
  data() {
    return {
      fields: [
        { label: 'Song Name', key: 'song_name', sortable: true },
        { label: 'Artist', key: 'artist.full_name', sortable: true },
        { label: 'Reference ID', key: 'reference_id', sortable: false },
      ],
      items: [],
    };
  },
  mounted() {
    fetch('https://kcatalog-stage.herokuapp.com/api/songs', {
      method: 'get',
    })
      .then((response) => {
        console.log(response);
        return response.json();
      })
      .then((jsonData) => {
        this.items = jsonData;
      })
      .catch((error) => {
        console.error(error);
      });
  },
};
</script>
