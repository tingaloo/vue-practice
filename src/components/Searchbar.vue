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
        @mouseover="hover = true"
        @mouseleave="hover = false"
        class="inline-block align-middle h-4"
        src="../assets/mic.png"
      />
      <div
        :class="[hover ? 'absolute' : 'hidden']"
        class="text-sm bg-black text-white px-2 py-1"
      >Search by Voice</div>
    </div>
  </div>
</template>

// v-bind:class="[isActive ? activeClass : '', errorClass]"

<script>
module.exports = {
  data: function() {
    return {
      greeting: "Hello",
      expandSearchBar: false,
      hover: false,
      searchResults: [
      { name: 'Vue got moves' },
      { name: 'Vue is pretty snappy' },
      { name: 'Vue is awesome!' }
    ]
    };
  }
};
</script>