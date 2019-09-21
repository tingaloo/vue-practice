import Vue from 'vue';

<template>
  <div
    v-bind:class="[expandSearchBar ? 'rounded-lg border-gray-400' : 'rounded-full']"
    class="flex justify-center border border-gray-200 py-2 w-3/5 flex-wrap"
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
        class="text-sm bg-black text-white px-2 py-1"
      >Search by Voice</div>
    </div>
    </div>
              <div class="bt-1 w-full border flex mx-2 mt-1 mb-2"
              v-if="expandSearchBar"></div>

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
  </div>
</template>


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
        { name: "Vue is awesome!" }
      ]
    };
  }
};
</script>