<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="movie-bar">
      <span class="movie-poster">
        <img
          v-on:click="showdetail"
          src="https://m.media-amazon.com/images/M/MV5BNjQ3NWNlNmQtMTE5ZS00MDdmLTlkZjUtZTBlM2UxMGFiMTU3XkEyXkFqcGdeQXVyNjUwNzk3NDc@._V1_SX300.jpg"
        />
       <ShowDetail/>
      </span>
      
      <div>Title</div>
    </div>
    <div>
      <button id="show-modal" v-on:click="addMovie" :isVisible="false" >Add Movie</button>
      <AddMovie />
    </div>
    
  </div>
</template>

<script>
import axios from "axios";
import { mapState } from 'vuex';
import ShowDetail from "./ShowDetail.vue";
import AddMovie from "./AddMovie.vue";
// import VModal from 'vue-js-modal';

export default {
  data () {
    return {
       // This value is set to the value emitted by the child
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
    //   this.$emit(this.isVisible);
     }
   },
  mounted() {
    console.log("hello");
    axios
      .get("https://www.omdbapi.com/?apikey=e0620bd4&s=harry potter")
      .then((res) => {
        mapState({
    
    countAlias: 'count',
  }) 
        console.log("res", res.data.Search);
      });
  },

};
console.log(mapState['countAlias'])
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  color: #7ba993;
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
