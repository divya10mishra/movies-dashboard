<template>
  <div class="hello">
    <h1>{{ this.test }}</h1>
    <div class="movie-bar">
      <span class="movie-poster">
        <img
          v-on:click="showdetail"
          src={{this.arrData[0].Poster}}
        />
       <ShowDetail :showDetails="showDetails"/>
      </span>
        <div>{{this.arrData[0].Title}}</div>
    </div>
    <div>
      <button id="show-modal" v-on:click="addMovie">Add Movie</button>
      <AddMovie :isVisible="isVisible" />
    </div>
    
  </div>
</template>

<script>
import axios from "axios";
import ShowDetail from "./ShowDetail.vue";
import AddMovie from "./AddMovie.vue";
// import VModal from 'vue-js-modal';

export default {
  data () {
    return {
       isVisible:false,
       showDetails:false,
       arrData:[]
    }
  },
  name: "MoviesList",
  components:{
    AddMovie, ShowDetail
  },
  props: {
    msg: String,
  },
   methods:{
     addMovie:function(){
      console.log("modal",this.isVisible)
       this.isVisible= true;
     },
     showdetail:function(){
       this.showDetails= !this.showDetails;
     }
   },
  mounted() {
    console.log("hello");
    axios
      .get("https://www.omdbapi.com/?apikey=e0620bd4&s=harry potter")
      .then((res) => {
        console.log("res", res.data.Search);
        this.arrData = res.data.Search;
      });
  },

};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  color: #7ba993;
  margin: 50px;
}

.movie-bar {
  max-height: 400px;
  max-width:200px;
  border: 1px solid #7ba993;
  margin: 80px;
  padding: 20px;
  border-radius: 5px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start ;
  color: #7ba993;
}

.movie-poster {
}
img {
  height: 100%;
  width: 100%;
  object-fit: fill;
}
button {
  max-height: 50px;
  color: #dd6755;
  border: 1px solid #7ba993;
  border-radius: 10px;
  font-size: 20px;
  padding: 10px;
  background-color: white;
}
</style>
