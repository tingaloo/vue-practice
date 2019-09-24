
<template>
  <div class="flex self-center justify-center h-screen flex-col justify-between">
    <div class="flex justify-between pt-4 px-2">
      <div class="flex">
        <a class="flex px-2 tracking-tight">About</a>
        <a class="flex px-2 tracking-tight">Store</a>
      </div>
      <div class="flex">
        <a class="px-2">Gmail</a>
        <a class="px-2">Images</a>
        <a class="px-2">Icon</a>
        <a class="flex mb-4 flex-col w-4 mx-2">
          <div class="flex w-full mb-1 justify-between">
            <div class="bg-gray-500 h-1 w-1"></div>
            <div class="bg-gray-500 h-1 w-1"></div>
            <div class="bg-gray-500 h-1 w-1"></div>
          </div>
          <div class="flex w-full my-1 justify-between">
            <div class="bg-gray-500 h-1 w-1"></div>
            <div class="bg-gray-500 h-1 w-1"></div>
            <div class="bg-gray-500 h-1 w-1"></div>
          </div>
          <div class="flex w-full my-1 justify-between">
            <div class="bg-gray-500 h-1 w-1"></div>
            <div class="bg-gray-500 h-1 w-1"></div>
            <div class="bg-gray-500 h-1 w-1"></div>
          </div>
        </a>
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
          v-scrollEvent:mouseover="luckyScroll"
          v-scrollEvent:mouseleave="stopLuckyScroll"
          class="px-2 mx-2 py-2 bg-gray-100 cursor-pointer border border-white hover:border-gray-500"
        >{{luckyText.name}}</div>
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
<style scoped>
.underline {
  text-decoration: underline;
  background-color: red;
}
</style>
<script>
const luckyOptions = [
  { name: "I'm feeling Doodly" },
  { name: "I'm feeling Playful" },
  { name: "I'm feeling Artistic" },
  { name: "I'm feeling Hungry" },
  { name: "I'm feeling Trendy" },
  { name: "I'm feeling Puzzled" },
  { name: "I'm feeling Stellar" }
];

export default {
  components: {
    Searchbar
  },
  name: "GoogleLayout",
  props: {},
  data: function() {
    return {
      luckyText: { name: "I'm feeling Lonely" },
      myScroll: undefined
    };
  },
  directives: {
    scrollEvent: {
      bind(el, binding) {
        el.addEventListener(binding.arg, binding.value);
      }
    }
  },
  methods: {
    luckyScroll() {
      setTimeout(() => {
        this.myScroll = setInterval(() => {
          this.luckyText =
            luckyOptions[Math.floor(Math.random() * luckyOptions.length)];
        }, 50);
      }, 500);
    },
    stopLuckyScroll() {
      setTimeout(() => {
        clearInterval(this.myScroll), (this.myScroll = undefined);
      }, 500);
    }
  }
};

import Searchbar from "./Searchbar.vue";
</script>