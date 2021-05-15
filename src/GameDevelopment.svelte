<svelte:head>
  <base target="_blank"/>
</svelte:head>
<style>
    .textBox{
      padding: 20px;
      border: 1px solid gray;
      
      border-radius: 5px;
    }
    .animated {
              -webkit-animation-duration: 1s;
              animation-duration: 1s;
              -webkit-animation-fill-mode: both;
              animation-fill-mode: both;
          }
  
          .animated.faster {
              -webkit-animation-duration: 500ms;
              animation-duration: 500ms;
          }
  
          .fadeIn {
              -webkit-animation-name: fadeIn;
              animation-name: fadeIn;
          }
  
          .fadeOut {
              -webkit-animation-name: fadeOut;
              animation-name: fadeOut;
          }
  
          @keyframes fadeIn {
              from {
                  opacity: 0;
              }
  
              to {
                  opacity: 1;
              }
          }
  
          @keyframes fadeOut {
              from {
                  opacity: 1;
              }
  
              to {
                  opacity: 0;
              }
          }
  </style>
  <script>
  import Footer from './Footer.svelte';
  import CTA from './CTA.svelte';
  import ShareSubmit from './ShareSubmit.svelte';
  import {link} from 'svelte-routing';
  import { onMount } from 'svelte';

  import localapi from './data/game.json';
  let resources = localapi["Sheet1"];

  let name="Game Development";
    
  let resBeginners = [];
  let resIntermediate = [];
  let resAdvanced = [];

  function filtering(){
    
    let filters=["Beginner","Intermediate","Advanced"]
        resBeginners = localapi.Sheet1.filter( i => filters[0].includes( i.D ) );
        resIntermediate = localapi.Sheet1.filter( i => filters[1].includes( i.D ) );
        resAdvanced = localapi.Sheet1.filter( i => filters[2].includes( i.D ) );
}

  onMount(()=>{
    filtering()
});
  
  </script>
  <div>
      <!-- Header Component-->
      <div class="font-inter flex flex-grow h-auto justify-center items-center py-10">
          <div class="text-center">
              <a href="/"><p class="text-5xl font-bold text-blue-700">Learning in Tech</p></a>
            <p class="text-3xl m-2">
              <strong>Game Development</strong>
            </p>
            <p class="textBox text-lg mt-2 m-5">
              <strong>Video Game Development</strong> is the process of developing a video game. <br>
                The effort is undertaken by a developer, ranging from a single person to an international team dispersed across the globe. <a class="text-blue-700" href="https://en.wikipedia.org/wiki/Video_game_development">(wiki.)</a><br/>
                Here is the list of top resources you can access to get started with Video Game Development (including 2D and 3D).
                <br />
              <br />
              <strong>Start learning {name} with <a class="text-blue-700" href='/tracker'>LIT Tracker.</a></strong>
            </p>
            <button class="bg-green hover:bg-green-100 text-gray-800 font-semibold py-2 px-4 border border-gray-400 rounded shadow" on:click={()=>{ resources = resBeginners }}>
              Beginner
            </button>
            <button class="bg-blue hover:bg-blue-100 text-gray-800 font-semibold py-2 px-4 border border-gray-400 rounded shadow" on:click={()=>{ resources = resIntermediate }}>
              Intermediate
            </button>
            <button class="bg-yellow hover:bg-yellow-100 text-gray-800 font-semibold py-2 px-4 border border-gray-400 rounded shadow" on:click={()=>{ resources = resAdvanced }}>
              Advanced
            </button>
            <button class="bg-white hover:bg-gray-100 text-gray-800 font-semibold py-2 px-4 border border-gray-400 rounded shadow" on:click={()=>{ resources = localapi['Sheet1'] }}>
              All
            </button>
          </div>
      </div>
     
      <div id="content">
      {#each resources as cat}
      <div class="flex bg-white shadow-lg rounded-lg mx-4 md:mx-auto mb-8 max-w-md md:max-w-2xl "><!--horizantil margin is just for display-->
        <div class="flex items-start px-4 py-6">
          <div class="">
              <div class="flex items-center justify-between">
                <small class="inline-block py-1 px-3 rounded bg-indigo-50 text-indigo-400 text-sm font-medium tracking-widest">{cat.D}</small>
                <!--small class="text-sm text-gray-700">22h ago</small-->
              </div>
              <!--p class="text-gray-700">Joined 12 SEP 2012. </p-->
              <h2 class="mt-3 font-semibold text-blue-700 text-lg"><a href={cat.C}>
                {cat.A}
              </a></h2>
              <p>{cat.B}</p>
          </div>
        </div>
      </div>
      {/each}
    </div>
  
    <!-- Add resource and share button-->
    <!-- ShareSubmit cat={name} -->
    <div class="p-50 text-center">
      <div class="font-semibold text-xl">Edit this on <a class="text-blue-700" href='https://github.com/dwivedithedev/LIT/blob/master/src/data/game.json'>Github.</a></div>
      <CTA />
      <Footer/>
    </div>
  </div>