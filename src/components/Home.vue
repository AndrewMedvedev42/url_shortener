 <template>
  <div>
    <div class="">
      <div class="card">
        <div class="card-body">
          <form @submit.prevent="submit(url)">
            <div class="form-group">
              <label for="url">Create short links for easy tracking and sharing</label>
              <textarea type="url" class="form-control" v-model="url" style="height:150px" />
            </div>
            <div class="for-group" v-show="shortUrl">
              <p>
                Short URL: :
                <a :href="shortUrl" target="_blank" rel="noopener noreferrer" class="text-primary">{{shortUrl}}</a>
              </p>
            </div>
            <div class="form-group">
              <button class="btn btn-primary" type="submit">Shorten URl</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template> 

<script>
import axios from "axios";
export default {
  data: () => {
    return {
      url: "",
      shortUrl: "",
    };
  },
  methods: {
    submit: async function (url) {
      try {
        const response = await axios.post(`${process.emv.VUE_APP_BACKEND_URL}/url`, {url});
        this.shortUrl = response.data.shortUrl;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script> 

<style>
  .card{
    width: 700px;
    margin: 30px auto 0;
  }
  @media screen and (max-width: 820px) {
    .card{
      width: 100%;
    }
  }
</style>