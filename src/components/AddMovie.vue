<template>
<modal>
 <div id="add-movie" v-if="isVisible" v-on:change="$emit('change', $event)">
   <div>
      <span class="input-title">Add Poster URL</span>
      <span> <input placeholder="Add Image URL" class="input-details"/></span>
   </div>
   <div>
      <span class="input-title">Title</span>
      <span> <input placeholder="Title" class="input-details"/></span>
   </div>
   <div>
      <span class="input-title">Type</span>
      <span> <input placeholder="Type" class="input-details"/></span>
   </div>
   <div>
      <span class="input-title">Year</span>
      <span> <input placeholder="Year" class="input-details"/></span>
   </div>
   <div>
      <span class="input-title">imdbID</span>
      <span> <input placeholder="imdbID" class="input-details"/></span>
   </div>
 </div>
 </modal>
</template>

<script>
export default {
  name: 'AddMovie',
  props: {
   isVisible: {
        type: Boolean,
       default: false
   }
  },
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.input-title{
  color:#dd6755;
  font-size: 10px;
}
 .input-details{
   border: 1px solid #7ba993;
   padding: 10px;
   border-radius: 10px;
   color:#dd6755;
 }
</style>
