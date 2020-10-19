<style>
  .textBox{
    padding: 20px;
    border: 1px solid gray;
    
    border-radius: 5px;
  }
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
      .cards-list {
      z-index: 0;
      width: 100%;
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
    }
    
    .card {
      margin: 30px auto;
      width: 300px;
      height: 300px;
      border-radius: 40px;
    box-shadow: 5px 5px 30px 7px rgba(0,0,0,0.25), -5px -5px 30px 7px rgba(0,0,0,0.22);
      transition: 0.4s;
    }
    
    .card .card_image {
      width: inherit;
      height: inherit;
      border-radius: 40px;
    }
    
    .card .card_image img {
      width: inherit;
      height: inherit;
      border-radius: 40px;
      object-fit: cover;
    }
    
    .card .card_title {
      text-align: center;
      border-radius: 0px 0px 40px 40px;
      font-family: sans-serif;
      font-weight: bold;
      font-size: 30px;
      margin-top: -80px;
      height: 40px;
    }
    
    .card:hover {
      transform: scale(0.9, 0.9);
      box-shadow: 5px 5px 30px 15px rgba(0,0,0,0.25), 
        -5px -5px 30px 15px rgba(0,0,0,0.22);
    }
    
    .title-white {
      color: white;
    }
    
    .title-black {
      color: black;
    }
    
    @media all and (max-width: 500px) {
      .card-list {
        /* On small screens, we are no longer using row direction but column */
        flex-direction: column;
      }
    }
    </style>
    <script>
        //both Link and link are different
      import { Router, Link, link, Route } from "svelte-routing";
      import Footer from './Footer.svelte';
      import logo from './img/logo.png';
      import { onMount } from 'svelte';

      function clearStorageUpdateContent(){
        localStorage.clear();
      }

      onMount(()=>{
        setTimeout(clearStorageUpdateContent,10000);
      })

    </script>
    <div ondragstart="return false">
      
    <div class="font-inter flex flex-grow pt-4 justify-center items-center">
      <div class="text-center">
        <a href="/">
        <img src={logo} alt="Logo" />
        <h1 class="text-2xl resize font-bold text-blue-400">Learning in Tech</h1>
        </a>
      </div>
    </div>

    <div class="font-inter flex flex-grow h-auto py-4 justify-center items-center">
      <div class="textBox text-center">
        <p class="text-lg">
          <strong>Started your journey in Tech.? Are you part of <span class="text-blue-400">#100DaysofCode</span>?
            <br>This stack will help you to learn specific technologies by providing FREE resources.</strong>
        </p>
      </div>
    </div>
    <!-- Row ONE of 4 Categories-->
      <div class="cards-list px-10">
      
            <div class="card 1">
                <div class="card_image"> 
                  <Router>
                  <a href="/AugmentedReality">
                    <img src="https://i.imgur.com/VzDSH6Z.jpg" /> 
                  </a>
                </Router>
                </div>
                <div class="card_title text-blue-500">
                  <a href="/AugmentedReality">
                    <p>Augmented Reality</p>
                  </a>
                </div>
            </div>
        
            <div class="card 1">
                <div class="card_image"> 
                  <a href="/VirtualReality">
                    <img src="https://i.imgur.com/29SYpw0.png" /> 
                  </a>
                </div>
                <div class="card_title text-blue-500">
                    <a href="/VirtualReality">
                    <p>Virtual Reality</p>
                </a>
                </div>
            </div>
            
            <div class="card 1">
                <div class="card_image"> 
                  <a href="/GameDevelopment">
                    <img src="https://i.imgur.com/vYQEgYx.png" /> 
                  </a>
                </div>
                <div class="card_title text-blue-500">
                    <a href="/GameDevelopment">
                    <p>Game Development</p>
                </a>
                </div>
            </div>
    
            <div class="card 1">
                <div class="card_image"> 
                  <a href="/InternetofThings">
                    <img src="https://i.imgur.com/s4ibcDU.jpg" /> 
                  </a>
                </div>
                <div class="card_title text-blue-500">
                    <a href="/InternetofThings">
                    <p>Internet of Things</p>
                </a>
                </div>
            </div>
      </div>
    
      
    <!-- Row TWO of 4 Categories-->
      <div class="cards-list px-10">
      
        <div class="card 1">
          <div class="card_image"> 
            <a href="/MachineLearning">
            <img src="https://i.imgur.com/lWk3GvR.jpg" />
            </a>
          </div>
          <div class="card_title text-blue-500">
            <a href="/MachineLearning">
            <p>Machine Learning</p>
            </a>
          </div>
        </div>
        
        <div class="card 2">
          <div class="card_image">
            <a href="/DeepLearning">
            <img src="https://i.imgur.com/1zydvP2.png" />
            </a>
           </div>
          <div class="card_title text-blue-500">
            <a href="/DeepLearning">
            <p>Deep Learning</p>
          </a>
          </div>
        </div>
        
        <div class="card 3">
          <div class="card_image">
            <a href="/ArtificialIntelligence">
            <img src="https://i.imgur.com/B0XxRQK.jpg" />
            </a>
          </div>
          <div class="card_title text-blue-500">
            <a href="/ArtificialIntelligence">
            <p>A.I.</p>
            </a>
          </div>
        </div>
          
        <div class="card 4">
          <div class="card_image">
            <a href="/Blockchain">
            <img src="https://i.imgur.com/zpEaAmU.png" />
            </a>
            </div>
          <div class="card_title text-blue-500">
            <a href="/Blockchain">
              <p>Blockchain</p>
            </a>
          </div>
        </div>
    
      </div>
    
      <!-- Row THREE of 4 Categories-->
      <div class="cards-list px-10">
      
        <div class="card 1">
          <div class="card_image">
            <a href="/BigData">
            <img src="https://i.imgur.com/28pCABK.png" /> 
            </a>
          </div>
          <div class="card_title text-blue-500">
            <a href="/BigData">
              <p>Big Data</p>
          </a>
          </div>
        </div>
        
        <div class="card 2">
          <div class="card_image">
            <a href="/DataScience">
            <img src="https://i.imgur.com/PfpJprq.png" />
            </a>
            </div>
          <div class="card_title text-blue-500">
            <a href="/DataScience">
            <p>Data Science</p>
          </a>
          </div>
        </div>
        
        <div class="card 3">
          <div class="card_image">
            <a href="/Automation">
            <img src="https://i.imgur.com/G96ou8Y.png" />
            </a>
          </div>
          <div class="card_title text-blue-500">
            <a href="/Automation">
            <p>Automation</p>
          </a>
          </div>
        </div>
          
        <div class="card 4">
          <div class="card_image">
            <a href="/Voice">
            <img src="https://i.imgur.com/VbbixtS.png" />
            </a>
            </div>
          <div class="card_title text-blue-500">
            <a href="/Voice">
            <p>Voice</p>
          </a>
          </div>
        </div>
      </div>

      <div class="font-inter flex flex-grow h-screen px-10 justify-center items-center">
        <div class="text-center">
          <p class="sm:text-5xl md:text-5xl lg:text-5xl xl:text-5xl font-bold text-blue-400">Learn with the #LITCommunity</p>
          <p class="sm:text-xl md:text-xl lg:text-2xl xl:text-2xl font-bold mt-4 mx-4">
            Meet, Share and Chill with other amazing learners from around the world.
          </p>
          <div class="mt-4">
          <button class="shiny-btn"><a href="https://discord.gg/A2jejy2"><img src="https://discord.com/assets/e7a3b51fdac2aa5ec71975d257d5c405.png" width="128px" height="64px" /></a></button>
          </div>
        </div>
      </div>
    
    
    
    <Footer/>
    </div>