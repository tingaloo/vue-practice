import Vue from 'vue';

<template>
  <div
    v-bind:class="[expandSearchBar ? 'rounded-lg' : 'rounded-full']"
    class="flex justify-center border border-gray-200 py-2 w-3/5 px-2"
  >
    <div class>
      <img class="inline-block align-middle h-4" src="../assets/searchIcon.png" />
    </div>
    <div class="flex-grow mx-2">
      <input
        @blur="expandSearchBar = !expandSearchBar"
        v-on:click="expandSearchBar = true"
        class="flex-grow w-full"
      />
      <ul id="example-1" v-if="expandSearchBar">
  <li v-for="result in searchResults" v-bind:key="result.name">
    {{ result.name }}
  </li>
</ul>
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
</template>


<script>
module.exports = {
  data: function() {
    return {
      greeting: "Hello",
      expandSearchBar: false,
      searchHover: false,
      searchResults: [
      { name: 'Vue got moves' },
      { name: 'Vue is pretty snappy' },
      { name: 'Vue is awesome!' }
    ],
    luckyOptions: [
      {name: "I'm feeling Doodly"},
      {name: "I'm feeling Playful"},
      {name: "I'm feeling Artistic"},
      {name: "I'm feeling Hungry"},
      {name: "I'm feeling Trendy"},
      {name: "I'm feeling Puzzled"},
      {name: "I'm feeling Stellar"}
    ],
    luckyHover: false
    };
  }
  
};
</script>