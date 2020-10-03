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
  transition: opacity 500ms;
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
  import { Router, Link, link, Route } from "svelte-routing";
  import { Email, HackerNews, Reddit, LinkedIn, Pinterest, Telegram, Tumblr, Vk, WhatsApp, Xing, Facebook, Twitter } from 'svelte-share-buttons-component';
 
 const url = window.location.href;
 let title = 'Hey everyone, Here is a resource to learn a new technology!';
 const desc = 'Learningin.tech is a resource for learning new technologies in your #100DaysofCode Journey. You can also join #LITcommunity for more!';

</script>
<div class="flex flex-grow justify-center items-center">
    <div class="text-center">
      <p class="textBox text-lg mt-2 m-5">
        Have something to add? <span class="text-blue-700"><a href="/Suggestions">Suggest a tutorial</a>.</span>
        <br>
        Like this list? <button class="text-blue-700"><a href="#popup1">Share it</a>.</button>
        <div id="popup1" class="overlay">
          <div class="popup">
            <span class="text-3xl resize font-bold text-blue-700">Share 💙</span>
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