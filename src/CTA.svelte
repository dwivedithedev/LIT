<script>
export let category;
</script>
<style>
    .shiny-btn {
      color: white;
      font-weight: bold;
      font-size: 1.5rem;
      text-decoration: none;
      text-transform: uppercase;
      padding: 20px 45px;
      background-color: #7289DA;
      transition: transform 500ms cubic-bezier(0.68, -0.55, 0.265, 1.55), background-position 800ms cubic-bezier(0.68, -0.55, 0.265, 1.55), box-shadow 500ms linear;
      background-image: url('data:image/svg+xml;utf8,<?xml version="1.0" encoding="utf-8"?><svg version="1.1" id="Livello_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"	 width="1296px" height="768px" viewBox="0 0 1296 768" enable-background="new 0 0 1296 768" xml:space="preserve"><g><polygon fill="#8694D1" points="766.6,1.2 -0.2,768 200.7,768 967.5,1.2 	"/></g><g><polygon fill="#8694D1" points="1094.8,1.2 328,768 528.9,768 1295.7,1.2 	"/></g></svg>');
      background-size: contain;
      background-position: -200px center;
      background-repeat: no-repeat;
      box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
    }
    .shiny-btn:hover {
      transform: scale(1.1);
      background-position: -60px;
      box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 3px 6px rgba(0, 0, 0, 0.23);
    }
    .shiny-btn:active {
      transform: scale(1);
      background-position: 500px;
      box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
    }
</style>
<div class="font-inter flex flex-grow h-screen px-10 justify-center items-center">
    <div class="text-center">
      <p class="sm:text-5xl md:text-3xl lg:text-5xl xl:text-5xl font-bold text-blue-400">Learn {category} with others!</p>
      <p class="sm:text-xl md:text-xl lg:text-2xl xl:text-2xl font-bold mt-4 mx-4">
        Join #LITcommunity to Meet, Share and Chill with amazing learners from around the world.
      </p>
      <div class="mt-4">
      <button class="shiny-btn"><a href="https://discord.gg/A2jejy2"><img src="https://discord.com/assets/e7a3b51fdac2aa5ec71975d257d5c405.png" width="128px" height="64px" /></a></button>
      </div>
    </div>
  </div>