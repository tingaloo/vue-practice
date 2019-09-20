<template>
  <div class="flex self-center justify-center h-screen flex-col justify-between">
    <div class="flex justify-between pt-4 px-2">
      <div>
        <a class="px-2 tracking-tight">About</a>
        <a class="px-2 tracking-tight">Store</a>
      </div>
      <div>
        <a class="px-2">Gmail</a>
        <a class="px-2">Images</a>
        <a class="px-2">Icon</a>
      </div>
    </div>
    <div class="flex flex-col">
      <div class="flex justify-center py-4">
        <img class="object-contain w-1/4" src="../assets/googleLogo.png" />
      </div>
      <div class="flex justify-center">
        <Searchbar />
      </div>
      <div class="flex justify-center pt-8">
        <div
          class="px-2 mx-2 py-2 bg-gray-100 cursor-pointer border border-white hover:border-gray-500"
        >Google Search</div>
        <div
          class="px-2 mx-2 py-2 bg-gray-100 cursor-pointer border border-white hover:border-gray-500"
        >I'm Feeling Lucky</div>
      </div>
    </div>
    <div class="flex justify-between bg-gray-100 py-4 px-4">
      <div>
        <a class="px-2 tracking-tight text-xs">Advertising</a>
        <a class="px-2 tracking-tight text-xs">Business</a>
        <a class="px-2 tracking-tight text-xs">How Search works</a>
      </div>
      <div>
        <a class="px-4 text-xs">Privacy</a>
        <a class="px-2 text-xs">Terms</a>
        <a class="px-2 text-xs">Settings</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
      components: {
    Searchbar
  },
  name: "GoogleLayout",
  props: {}
};

import Searchbar from './Searchbar.vue';
</script>