<style>
    .textBox{
      padding: 20px;
      border: 1px solid gray;
      
      border-radius: 5px;
    }
    
.overlay {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.7);
  transition: opacity 600ms;
  visibility: hidden;
  opacity: 0;
}
.overlay:target {
  visibility: visible;
  opacity: 1;
}

.popup {
  margin: 70px auto;
  padding: 20px;
  background: #fff;
  border-radius: 5px;
  width: 30%;
  position: relative;
  transition: all 3s ease-in-out;
}

.popup h2 {
  margin-top: 0;
  color: #333;
  font-family: Tahoma, Arial, sans-serif;
}
.popup .close {
  position: absolute;
  top: 20px;
  right: 30px;
  transition: all 200ms;
  font-size: 30px;
  font-weight: bold;
  text-decoration: none;
  color: #333;
}
.popup .close:hover {
  color: #7289DA;
}
.popup .content {
  max-height: 30%;
  overflow: auto;
  padding: 10%;
}

@media screen and (max-width: 700px){
  .box{
    width: 70%;
  }
  .popup{
    width: 70%;
  }
}
</style>
<script>
  export let cat;
  import { Router, Link, link, Route } from "svelte-routing";
  import { Email, HackerNews, Reddit, LinkedIn, Pinterest, Telegram, Tumblr, Vk, WhatsApp, Xing, Facebook, Twitter } from 'svelte-share-buttons-component';
 
 const url = window.location.href;
 let title = 'Hey everyone, Here is a totally free list of resources to learn '+cat;
 const desc = 'Learningin.tech is a resource for learning new technologies in your #100DaysofCode Journey. You can also join #LITcommunity for more!';

</script>
<section class="text-gray-700 body-font">
  <div class="container flex flex-wrap px-5 py-24 mx-auto items-center">
    <div class="md:w-1/2 md:pr-12 md:py-8 md:border-r md:border-b-0 mb-10 md:mb-0 pb-10 border-b border-gray-300">
      <h1 class="sm:text-3xl text-2xl font-medium title-font mb-2 text-gray-900">Contribute a Resource 👨‍🎓</h1>
      <p class="leading-relaxed text-base">Do you have a resource which can be helpful to others who are learning {cat}? We would love to have you contribute it.</p>
      <a class="text-blue-600 inline-flex items-center mt-4" href="https://github.com/dwivedithedev/LIT">See on Github
        <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-4 h-4 ml-2" viewBox="0 0 24 24">
          <path d="M5 12h14M12 5l7 7-7 7"></path>
        </svg>
      </a>
    </div>
    <div class="flex flex-col md:w-1/2 md:pl-12">
      <h1 class="sm:text-3xl text-2xl font-medium title-font mb-2 text-gray-900">Share This Resource 💙</h1>
      <p class="leading-relaxed text-base">Sharing is caring. Forward this resource to a friend or colleague who you think can benefit from.</p>
      <a class="text-blue-600 inline-flex items-center mt-4" href="#popup1">Click To Share
        <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-4 h-4 ml-2" viewBox="0 0 24 24">
          <path d="M5 12h14M12 5l7 7-7 7"></path>
        </svg>
      </a>
      <div id="popup1" class="overlay">
        <div class="popup">
          <span class="text-3xl resize font-bold text-blue-700">Share </span>
          <a class="close" href="#">&times;</a>
          <div class="content">
            <Email subject="{title}" body="{desc} {url}" />
            <Twitter class="share-button" text="{title}" {url} />
            <Reddit class="share-button" {title} {url} />
            <LinkedIn class="share-button" {url} />
            <Telegram class="share-button" text={title} {url} />
            <Facebook class="share-button" {url} />
            <HackerNews class="share-button" {title} {url} />
          </div>
        </div>
      </div>
    </div>
  </div>
</section>