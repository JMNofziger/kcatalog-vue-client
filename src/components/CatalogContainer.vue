<template>
  <div class="catalog-container">
    <b-form-group
        label="Filter"
        label-for="filter-input"
        label-cols-sm="3"
        label-align-sm="right"
        label-size="sm"
        class="mb-0"
      >
      <b-input-group size="sm">
        <b-form-input
          id="filter-input"
          v-model="filter"
          type="search"
          placeholder="Type to Search"
        ></b-form-input>

        <b-input-group-append>
          <b-button :disabled="!filter" @click="filter = ''">Clear</b-button>
        </b-input-group-append>
      </b-input-group>
    </b-form-group>
    <b-table striped hover :filter="filter" @filtered="onFiltered" :fields=fields :items="items">
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
  methods: {
    onFiltered(filteredItems) {
      // Trigger pagination to update the number of buttons/pages due to filtering
      this.totalRows = filteredItems.length;
      //  this.currentPage = 1
    },
  },
};
</script>
