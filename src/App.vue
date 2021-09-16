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
        selectedPage:'Home',
        albums:[
          {name:'drive'},
          {name:'zhu'},
          {name:'All New Indie'},
          {name:'Mellow'},
          {name:'Classic Road Trip Songs'},
          {name:'Party Songs'},
          {name:'Relaxing music'},
        ]
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
      <div class="mx-2 mb-5">
        <button v-for="(page,index) in pages" :key="index" @click="selectedPage=page.name" :class="  `w-full  text-sm font-semibold rounded px-3 py-2 flex items-center justify-start ${ selectedPage === page.name ? 'bg-light text-white' : 'text-lightest' }`">
          <span class="material-icons mr-3">{{page.icon}}</span> <p>{{page.name}}</p>
        </button>
      </div>
      <div class="mx-5">
        <h1 class="text-xs text-lightest tracking-widest uppercase mb-3">Playlist</h1>
        <button class="flex items-center justify-start opacity-75 hover:opacity-100  mb-2">
          <div class=" bg-white text-dark h-8 w-8 flex items-center text-2xl font-bold justify-center mr-3">+</div>
          <p class="text-sm text-white font-semibold">Create Playlist</p>
        </button>
        <button class="flex items-center justify-start opacity-75 hover:opacity-100 mb-2">
          <div class="bg-gradient-to-br from-blue-800  to-blue-300  text-white h-8 w-8 flex items-center justify-center mr-3"><span class="material-icons text-base">favorite</span></div>
          <p class="text-sm text-white font-semibold">Liked Songs</p>
        </button>
        <div class="h-px w-full bg-light my-3 "></div>
        <div class="mx-5">
          <div class="w-full h-10 overflow-y-scroll ">
            <p v-for="album,i in albums" :key="i" class="text-lightest hover:text-white text-sm py-1">{{album.name}}</p>
          </div>
          <button class="flex items-center justify-start text-lightest hover:text-white py-2">
            <span class="material-icons text-base  mr-3 border border-lightest rounded-full block h-6 w-6">keyboard_arrow_down</span>
            <p class="text-sm font-semibold">Install App</p>
          </button>
        </div>

      </div>
              <div class="relative mt-4">
          <img src="https://i4.hurimg.com/i/hurriyet/75/770x0/5f007af7d3806c129c7039f3.jpg" alt="" class=" h-50 object-cover object-center">
          <div class="w-full h-full absolute top-0 flex justify-end items-start p-2 opacity-0 hover:opacity-100 transition-opacity">
            <div class="bg-black rounded-full h-6 w-6 flex items-center justify-center ">
              <span class="material-icons text-white">keyboard_arrow_down</span>
            </div>
          </div>
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
    <div class="w-full bg-light " style="height:12vh;">

    </div>
</div>
</template>

<style>

</style>
