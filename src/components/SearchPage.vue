
<template>
  <div class="flex self-center h-screen flex-col">
    <div class="flex w-7/12 flex-wrap">
        <div class="flex justify-center w-1/5">
        <img class="object-contain w-2/5" src="../assets/googleLogo.png" />
      </div>
      <div class="flex w-4/5">
                <Searchbar />
        </div>

      <div class="flex w-1/5 ">
      
      </div>
            <div class="flex w-4/5 ">
      <div class="mx-2 py-2">News</div>
      <div class="mx-2 py-2">News</div>
      <div class="mx-2 py-2">News</div>
      <div class="mx-2 py-2">News</div>
      <div class="mx-2 py-2">Vidoe</div>

      </div>
        </div>
    <div  class="bt-1 w-full flex mt-1 mb-2 border-t-2">
      </div>
    <div class="flex w-7/12">
      <div class="flex w-1/5">
        </div>
        <div class="flex w-4/5 flex-wrap">
        <div class="flex w-full">
        About 5,450,000 results (0.43 seconds) 
        </div>
        <div class="flex w-full">
          Top Stories
          </div>
          <div class="flex w-1/3 p-2">
            <Card />
          </div>
          <div class="flex w-1/3 p-2">
            <Card />
          </div>
          <div class="flex w-1/3 p-2">
            <Card />
          </div>
        </div>
      </div>
  

  </div>
</template>

<script>


export default {
  components: {
    Searchbar,
    Card
  },
  name: "SearchPage",
  props: {},
  data: function() {
    return {

    };
  },
  directives: {

  },
  methods: {
  }
};

import Searchbar from "./Searchbar.vue";
import Card from "./Card.vue";
import axios from 'axios';
</script>