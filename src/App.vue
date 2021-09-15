<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
// import HelloWorld from './components/HelloWorld.vue'
</script>

<script>
export default{
  data() {
    return {
      pages:[
        {id:1,name:'Home', icon:'home'},
        {id:2,name:'Search', icon:'search'},
        {id:3,name:'Your Library', icon:'library_books'},
      ],
        selectedPage:'Home'
    }
  },
}
</script>

<template>
<div class="bg-dark h-screen">
  <div class="flex" style="height:88vh;">
    <!-- side nav -->
    <div class="w-56 bg-black h-full flex-none" >
      <div class="p-6">
      <img class="h-10" style="filter:brightness(0) inver(1);" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fs22.q4cdn.com%2F540910603%2Ffiles%2Fdesign%2FSpotify_Logo_White.png&f=1&nofb=1" alt="">
      </div>
      <div class="mx-2">
        <button v-for="(page,index) in pages" :key="index" @click="selectedPage=page.name" :class="  `w-full  text-sm font-semibold rounded px-3 py-2 flex items-center justify-start ${ selectedPage === page.name ? 'bg-light text-white' : 'text-lightest' }`">
          <span class="material-icons mr-3">{{page.icon}}</span> <p>{{page.name}}</p>
        </button>
      </div>
    </div>
    <!-- main content -->
    <div class="w-full h-full relative">

      <!-- header -->
      <div class="w-full sticky top-0 p-2">
      </div>
    </div>
  </div>
    <!-- paybar -->
    <div class="w-full bg-light" style="height:12vh;">

    </div>
</div>
</template>

<style>

</style>
