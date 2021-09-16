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
        ],
        accountHover:true,
        topCards:[
          {src:'https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fsocietyofrock.com%2Fwp-content%2Fuploads%2F2016%2F07%2Fjudas-priest-use.jpg&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'},
          {src:'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fstatic.standard.co.uk%2Fs3fs-public%2Fthumbnails%2Fimage%2F2018%2F01%2F22%2F11%2Fsmiths.jpg&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'},
          {src:'https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fsocietyofrock.com%2Fwp-content%2Fuploads%2F2016%2F07%2Fjudas-priest-use.jpg&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'},
          {src:'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fstatic.standard.co.uk%2Fs3fs-public%2Fthumbnails%2Fimage%2F2018%2F01%2F22%2F11%2Fsmiths.jpg&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'},
          {src:'https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fsocietyofrock.com%2Fwp-content%2Fuploads%2F2016%2F07%2Fjudas-priest-use.jpg&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'},
          {src:'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.thoughtco.com%2Fthmb%2FgykQv9yc-uTYSFJUsJ_NGXfIIuI%3D%2F6300x4200%2Ffilters%3Afill(auto%2C1)%2FGettyImages-587240081-57ef12a35f9b586c35c93ac4.jpg&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'}
        ],
        secondCards:[
          {src:'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fdailymix-images.scdn.co%2Fv2%2Fimg%2Fb8aaf4b179bb0a52f29a810fdb0f9d5c16ec2c75%2F1%2Fen%2Flarge&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'},
          {src:'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fdailymix-images.scdn.co%2Fv2%2Fimg%2F65b17276698a6f067778e00a43b5f8f369423bb5%2F3%2Fen%2Flarge&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'},
          {src:'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fdailymix-images.scdn.co%2Fv2%2Fimg%2Fb8aaf4b179bb0a52f29a810fdb0f9d5c16ec2c75%2F1%2Fen%2Flarge&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'},
          {src:'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fdailymix-images.scdn.co%2Fv2%2Fimg%2F3416c5c5e30dcafbb24e40b69339312f4ba29b56%2F4%2Fen%2Flarge&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'},
          {src:'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fdailymix-images.scdn.co%2Fv2%2Fimg%2F330f9806621bc0fe67f5c06f2f1f8df53d011b4e%2F4%2Fen%2Flarge&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'},
          {src:'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fdailymix-images.scdn.co%2Fv2%2Fimg%2F93fec27f9aac86526b9010e882037afbda4e3d5f%2F2%2Fen%2Flarge&f=1&nofb=1',title:'Daily Mix',artist:'By Spotify'}
        ],
        pause:false,
    }
  },
  methods: {
    playSong(){
      this.pause = ! this.pause
      if(this.pause){
        var audio = new Audio('./song.mp3')
        audio.play()
      }
    }
    
  },
}
</script>

<template>
<div class="bg-dark h-screen">
  <div class="flex" style="height:88vh;">
    <!-- side nav -->
    <div class="w-56 bg-black h-full flex-none z-30" >
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
          <div class="relative mt-4 z-0">
          <img src="https://i4.hurimg.com/i/hurriyet/75/770x0/5f007af7d3806c129c7039f3.jpg" alt="" class=" h-60 mt-24 object-cover object-center ">
          <div class="w-full h-full absolute top-0 flex justify-end items-start p-2 opacity-0 hover:opacity-100 transition-opacity">
            <div class="bg-black rounded-full h-6 w-6 flex items-center justify-center ">
              <span class="material-icons text-white">keyboard_arrow_down</span>
            </div>
          </div>
        </div>
    </div>
    <!-- main content -->
    <div class="w-full h-full relative overflow-y-scroll">

      <!-- header -->
      <div class="w-full sticky top-0 py-4 px-6 flex items-center justify-between bg-darkest z-40">
        <div class=" flex items-center">
          <button class="rounded-full bg-black w-8 h-8 text-white flex items-center justify-center mr-3">
              <span class="material-icons text-white">keyboard_arrow_left</span>
          </button>
          <button class="rounded-full bg-black w-8 h-8 text-white flex items-center justify-center">
              <span class="material-icons text-white">keyboard_arrow_right</span>
          </button>
        </div>
        <div class="relative">

         <button class="rounded-full bg-light h-8 px-1  text-white flex items-center justify-bet opacity-75 hover:opacity-100" type="button" @click="accountHover= !accountHover">
           <img src="https://yt3.ggpht.com/yti/APfAmoG83tGd_mcU-UmVuAYB2jRsFEYVk-ePyBDOazilaw=s88-c-k-c0x00ffffff-no-rj-mo" alt="" class="w-6 h-6 rounded-full mr-2">
           <p class="text-xs mr-1">Ulaş Can Demirbağ</p>
              <span class="material-icons text-white">{{ accountHover ? 'arrow_drop_down' :'arrow_drop_up'}}</span>
          </button>
          <div :class=" ` absolute text-lightest  bg-light w-full rounded  mt-1   text-sm   ${accountHover ? 'hidden' :'block'}` ">
            <button class="py-2  opacity-75 hover:opacity-100 w-full text-left pl-8" >Account</button>
            <div class="h-px w-full border-t border-lightest"></div>
            <button class="py-2  opacity-75 hover:opacity-100 w-full text-left pl-8">Log out</button>
          </div>
        </div>
      </div>
      <!-- cards -->
      <div>
        <div class=" px-6 flex items-center justify-between">
        <h1 class="pl-2 text-2xl font-semibold text-white tracking-wider hover:underline">Recently Played</h1>
        <h2 class="pr-8 text-xs pt-4 text-lightest uppercase tracking-wider hover:underline mb-3">See All</h2>
        </div>
        <div class="w-full flex flex-wrap px-6 py-3">
          <div v-for="card,i in secondCards" :key="i" class="p-2 w-1/1 md:w-1/2 lg:w-1/4 xl:w-1/6 relative">
            <div class="absolute opacity-0 hover:opacity-100 transition-opacity w-full h-full flex items-end justify-end p-8">
                <div class="bg-green rounded-full  h-10 w-10 flex items-center justify-center">
                  <span class="material-icons text-white text-2xl">
                      play_arrow
                  </span>
                </div>
            </div>
            <div  class=" bg-light w-full h-auto p-5  rounded-md">
              <img :src="card.src" alt="" class="w-full h-auto shadow mb-2  object-center object-cover">
              <h2 class="text-sm font-semibold text-white tracking-wide">{{card.title}}</h2>
              <h3 class="text-xs  text-lightest tracking-wide pb-5">{{card.artist}} </h3>
            </div>
          </div>
        </div>
       <div class=" px-8 mt-8">
        <h1 class=" text-2xl font-semibold text-white tracking-wider hover:underline">Made For You</h1>
        <h2 class="text-sm  text-lightest">Get better recommendations the more you listen.</h2>
        </div>
        <div class="w-full flex flex-wrap px-6 py-2">
          <div v-for="card,i in topCards" :key="i" class="p-2 w-1/1 md:w-1/2 lg:w-1/4 xl:w-1/6 relative">
                      <div class="absolute opacity-0 hover:opacity-100 transition-opacity w-full h-full flex items-end justify-end p-8">
                <div class="bg-green rounded-full  h-10 w-10 flex items-center justify-center">
                  <span class="material-icons text-white text-2xl">
                      play_arrow
                  </span>
                </div>
            </div>
            <div  class=" bg-light w-full h-auto p-5  rounded-md">
              <img :src="card.src" alt="" class="shadow mb-2 h-full  w-full object-top object-cover" >
              <h2 class="text-sm font-semibold text-white tracking-wide">{{card.title}}</h2>
              <h3 class="text-xs  text-lightest tracking-wide pb-5">{{card.artist}} </h3>
            </div>
          </div>
        </div>
         <div class=" px-8 mt-8">
        <h1 class=" text-2xl font-semibold text-white tracking-wider hover:underline">Made For You</h1>
        <h2 class="text-sm  text-lightest">Get better recommendations the more you listen.</h2>
        </div>
        <div class="w-full flex flex-wrap px-6 py-2">
          <div v-for="card,i in topCards" :key="i" class="p-2 w-1/1 md:w-1/2 lg:w-1/4 xl:w-1/6 relative">
                      <div class="absolute opacity-0 hover:opacity-100 transition-opacity w-full h-full flex items-end justify-end p-8">
                <div class="bg-green rounded-full  h-10 w-10 flex items-center justify-center">
                  <span class="material-icons text-white text-2xl">
                      play_arrow
                  </span>
                </div>
            </div>
            <div  class=" bg-light w-full h-auto p-5  rounded-md">
              <img :src="card.src" alt="" class="shadow mb-2 h-full  w-full object-top object-cover" >
              <h2 class="text-sm font-semibold text-white tracking-wide">{{card.title}}</h2>
              <h3 class="text-xs  text-lightest tracking-wide pb-5">{{card.artist}} </h3>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
    <!-- paybar -->
    <div class="w-full bg-light flex items-center justify-between px-3 border-t border-darkest sticky z-50" style="height:12vh;">
      <div class="flex items-center w-3/12">
        <div>
          <h2 class="text-sm text-white tracking-wide " >Kurtlar Vadisi - Vadi Pusulu</h2>
          <h3 class="text-xs text-lightest tracking-wide">Harekaat Müziği</h3>
        </div>
        <span class="material-icons text-xl text-green mx-4 hover:text-white">favorite</span>
        <span class="material-icons text-xl text-lightest hover:text-white">picture_in_picture_alt</span>
      </div>
  
      <div class="flex  flex-col justify-center w-5/12 items-center">
        <div class="flex items-center">
          <button class=" text-lightest mx-5 hover:text-white"><span class="material-icons text-lg">shuffle</span></button>
          <button class=" text-lightest hover:text-white"><span class="material-icons text-lg">skip_previous</span></button>
          <button @click="playSong" class=" text-lightest h-8 w-8 flex items-center justify-center border rounded-full border-lightest  hover:text-white mx-5"><span v-if="!pause" class="material-icons text-2xl">play_arrow</span><span v-else class="material-icons text-2xl">pause</span></button>
          <button class=" text-lightest hover:text-white"><span class="material-icons text-lg">skip_next</span></button>
          <button class=" text-lightest mx-5 hover:text-white"><span class="material-icons text-lg">repeat</span></button>
        </div>
        <div class="w-full flex items-center justify-center mt-3">
          <p class="text-xs text-lightest mr-1">1:50</p>
          <div class=" h-1 bg-darkest rounded-full flex w-full items-center">
            <div class=" h-1 bg-green rounded-full w-1/2">
            </div>
            <div class="h-3 w-3 bg-white rounded-full -ml-1 shadow">
            </div>
          </div>
          <p class="text-xs text-lightest ml-1">3:00</p>
        </div>
      </div>

      <div class="flex items-center w-3/12 justify-end">
        <span class="material-icons text-lightest hover:text-white">playlist_play</span>
        <span class="material-icons text-xl text-lightest mx-3 hover:text-white">important_devices</span>
        <span class="material-icons text-xl text-lightest hover:text-white">volume_up</span>
        <div class="w-20 bg-lightest rounded-full h-1 ml-1">
        </div>
      </div>
    </div>
</div>
</template>

<style>

</style>
