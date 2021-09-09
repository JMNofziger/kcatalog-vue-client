<template>
<div class="catalog-container">
  <b-container fluid>
  <b-row>
    <b-col lg="6" offset-lg="3">
    <b-form-group description="Filter the catalog with keywords">
      <b-input-group size="md">
        <b-form-input id="filter-input" v-model="filter" type="search" placeholder="Type to Search">
        </b-form-input>

        <b-input-group-append>
          <b-button :disabled="!filter" @click="filter = ''">Clear</b-button>
        </b-input-group-append>
      </b-input-group>
    </b-form-group>
    </b-col>
  </b-row>
  </b-container>

  <b-table striped hover :filter="filter" :fields=fields :items="items">
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
      filter: null,
      filterOn: [],
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
