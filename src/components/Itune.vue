<template>
  <div>
  <input type="text col-sm" class="btn btn-info " v-model="textSearch " />
  <button @click="searchData()" class="btn btn-info ">Search</button> 
  <!--{{List}}-->
  
  <div class="mt-5 mb-5 col-sm ">
  <div class="box">
  
  <b-card-group columns>
  <b-card
  v-for="data in List" :key="data.mal_id"
    :title="data.title"
    :img-src="data.image_url"
    img-alt="Image"
    img-top 
    tag="article"
    style="max-width: 20rem; "
    
  >
    <b-card-text>
      {{data.synopsis}}<br>Start date : {{data.start_date}}<br>
      End date : {{data.end_date}}
    </b-card-text>
    <b-button :href="data.url" variant="outline-primary">Ling.....</b-button>
  </b-card>
  </b-card-group>
  </div>
  </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      List: null,
      textSearch: "",
    };
  },
  methods: {
    searchData() {
      axios
        .get("https://api.jikan.moe/v3/search/anime?q=" +this.textSearch+"page=1")
        .then((response) => {
          this.List = response.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>
<style>
.box {
 background-color:rgb(50, 50, 50);
  padding: 35px;
  margin: 30px;
}
</style>