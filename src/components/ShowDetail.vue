 <template>

 <div class="deatils-poster" v-if="showDetails">
        <div>
          <span class="input-title">Type:</span>
         <span></span>
        </div>
        <div>
          <span class="input-title">Year:</span>
         <span></span>
        </div>
        <div>
          <span class="input-title">imdbID:</span>
         <span></span>
        </div>
</div>

</template>

<script>
export default {
  name: "ShowDetail",
  props: {
    showDetails:{
       type: Boolean,
       default: false
    }
  },
  }
</script>

<style>
.deatils-poster{
  background-color:#7db4a2;
  color: black;
  padding: 5px;
}
</style>