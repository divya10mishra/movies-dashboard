 <template>
<modal>
 <div class="deatils-poster">
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
</modal>
</template>

<script>
export default {
  name: "ShowDetail",
  props: {
    
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