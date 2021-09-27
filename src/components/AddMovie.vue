<template>
<modal>
 <div id="add-movie" v-if="isVisible">
   <div class="modal-fields">
      <span class="input-title">Add Poster URL</span>
      <span> <input placeholder="Add Image URL" class="input-details" v-model="poster"/></span>
   </div>
   <div class="modal-fields">
      <span class="input-title">Title</span>
      <span> <input placeholder="Title" class="input-details" v-model="title"/>}</span>
   </div>
   <div class="modal-fields">
      <span class="input-title">Type</span>
      <span> <input placeholder="Type" class="input-details" v-model="type"/></span>
   </div>
   <div class="modal-fields">
      <span class="input-title">Year</span>
      <span> <input placeholder="Year" class="input-details" v-model="year"/></span>
   </div>
   <div class="modal-fields">
      <span class="input-title">imdbID</span>
      <span> <input placeholder="imdbID" class="input-details" v-model="imdb"/></span>
   </div>
    <button id="preview" v-on:click.prevent="showPreview">{{Preview}}</button>
 </div>

<div class="preview-deatils" v-if="previewAllowed">
   <div>{{poster1}}</div>
   <div>Title: {{title1}}</div>
   <div>Type: {{type1}}</div>
   <div>Tear: {{year1}}</div>
   <div>imdbID: {{imdb1}}</div>
</div>

 </modal>
</template>

<script>
export default {
  name: 'AddMovie',
  data () {
    return {
       previewAllowed:false,
       Preview:'Show Preview',
       poster:'',
       title:'',
       type:'',
       year:'',
       imdb:''
    }
  },
  props: {
   isVisible: {
        type: Boolean,
       default: false
   }
  },
  methods:{
      showPreview:function() 
      {
        this.previewAllowed=!this.previewAllowed;
        this.poster =this.poster1;
        this.title=this.title1;
        this.type=this.type1;
        this.year=this.year1;
        this.imdb=this.imdb1;
        if(this.previewAllowed){
          this.Preview="Hide Preview"
        }
        else{
            this.Preview="Show Preview"
        }
      },

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
modal{
  display: flex;
  item:2;
  justify-content: space-evenly;
}
#add-movie{
  max-width: 500px;
}
.input-title{
  color:#dd6755;
  font-size:20px;
  margin:5px;
}
 .input-details{
   border: 1px solid #7ba993;
   padding: 10px;
   border-radius: 10px;
   color:#dd6755;
 }
 .modal-fields{
   margin:10px;
   display:flex;
   justify-content: space-between;
 }
 button {
  max-height: 35px;
  color: #dd6755;
  border: 1px solid #7ba993;
  border-radius: 10px;
  font-size: 15px;
  padding: 10px;
  background-color: white;
}
.preview-deatils{
  border: 1px solid #7ba993;
  max-height: 200px;
  padding: 15px;
}
</style>
