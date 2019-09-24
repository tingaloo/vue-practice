<template>
  <div class="container mx-auto py-10">
    {{info}}

  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
    info:null
  },
  mounted() {
      let uri = 'https://api.reddit.com/subreddits/popular.json?limit=10'

    axios
      .get(uri)
      .then(response => (this.info = response))

  }
};
import axios from 'axios';

</script>
