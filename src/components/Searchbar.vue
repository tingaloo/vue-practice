import Vue from 'vue';

<template>
  <div
    v-bind:class="[expandSearchBar ? 'rounded-lg border-gray-400 absolute' : 'rounded-full w-full']"
    class="flex justify-center border border-gray-200 py-2 flex-wrap bg-white"
  >
    <div class="flex w-full px-2">
      <div class>
        <img class="inline-block align-middle h-4" src="../assets/searchIcon.png" />
      </div>
      <div class="flex-grow mx-2">
        <input
          @blur="expandSearchBar = !expandSearchBar"
          v-on:click="expandSearchBar = true"
          class="flex-grow w-full outline-none"
        />
      </div>

      <div class>
        <img
          @mouseover="searchHover = true"
          @mouseleave="searchHover = false"
          class="inline-block align-middle h-4"
          src="../assets/mic.png"
        />
        <div
          :class="[searchHover ? 'absolute' : 'hidden']"
          class="text-sm bg-black text-white px-2 py-1 z-50"
        >Search by Voice</div>
      </div>
    </div>
                  <div 
                  class="bt-1 w-full flex mx-2 mt-1 mb-2 border-t-2"
              v-if="expandSearchBar">
              
              </div>

        <div class="flex w-full">
    <ul id="example-1" v-if="expandSearchBar" class="py-2 w-full">
      <li
        v-for="result in searchResults"
        v-bind:key="result.name"
        class="flex hover:bg-gray-200 py-2 px-2 w-full "
      >
      <div class="flex flex-grow cursor-default">
        {{ result.name }}
        </div>
        <a class="flex flex-none cursor-pointer">Remove</a>
        </li>
    </ul>
  </div>


        <!-- <div 
        style="margin-top: -.5rem"
        class=" w-3/5 absolute border border-gray-400 border-t-0 z-10 bg-white ">
              <div 
    class="bt-1 w-11/12 border flex  mt-1  z-20 flex items-center">
    </div>
      <ul id="example-1" class="py-2 w-full">
        <li
          v-for="result in searchResults"
          v-bind:key="result.name"
          class="flex hover:bg-gray-200 py-2 px-2 w-full"
        >
          <div class="flex flex-grow cursor-default">{{ result.name }}</div>
          <a class="flex flex-none cursor-pointer">Remove</a>
        </li>
      </ul>
    </div> -->


</div>
</template>
        // v-bind:class="[expandSearchBar ? 'visible' : 'invisible']"


<script>
module.exports = {
  data: function() {
    return {
      greeting: "Hello",
      expandSearchBar: false,
      searchHover: false,
      searchResults: [
        { name: "Vue got moves" },
        { name: "Vue is pretty snappy" },
        { name: "Vue is awesome!" },
         { name: "Vue got moves" },
        { name: "Vue is pretty snappy" }
      ]
    };
  }
};
</script>