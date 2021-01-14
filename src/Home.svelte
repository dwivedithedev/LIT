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

    </script>
    <div ondragstart="return false">
      <header class="relative w-full px-8 text-gray-700 bg-white body-font" >
        <div class="container flex flex-col flex-wrap items-center justify-between py-5 mx-auto md:flex-row max-w-7xl">
            <a href="#" class="relative z-10 flex items-center w-auto text-2xl font-extrabold leading-none text-black select-none">LearningIn.Tech</a>
    
            <nav class="top-0 left-0 z-0 flex items-center justify-center w-full h-full py-5 -ml-0 space-x-5 text-base md:-ml-5 md:py-0 md:absolute">
                <a href="#categories" class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900">
                    <span class="block">AI</span>
                    <span class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden">
                        <span x-show="hover" class="absolute inset-0 inline-block w-full h-1 h-full transform bg-gray-900" x-transition:enter="transition ease duration-200" x-transition:enter-start="scale-0" x-transition:enter-end="scale-100" x-transition:leave="transition ease-out duration-300" x-transition:leave-start="scale-100" x-transition:leave-end="scale-0"></span>
                    </span>
                </a>
                <a href="#categories" class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900">
                    <span class="block">ML</span>
                    <span class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden">
                        <span x-show="hover" class="absolute inset-0 inline-block w-full h-1 h-full transform bg-gray-900" x-transition:enter="transition ease duration-200" x-transition:enter-start="scale-0" x-transition:enter-end="scale-100" x-transition:leave="transition ease-out duration-300" x-transition:leave-start="scale-100" x-transition:leave-end="scale-0"></span>
                    </span>
                </a>
                <a href="#categories" class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900">
                    <span class="block">AR</span>
                    <span class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden">
                        <span x-show="hover" class="absolute inset-0 inline-block w-full h-1 h-full transform bg-gray-900" x-transition:enter="transition ease duration-200" x-transition:enter-start="scale-0" x-transition:enter-end="scale-100" x-transition:leave="transition ease-out duration-300" x-transition:leave-start="scale-100" x-transition:leave-end="scale-0"></span>
                    </span>
                </a>
                <a href="#categories" class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900">
                    <span class="block">VR</span>
                    <span class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden">
                        <span x-show="hover" class="absolute inset-0 inline-block w-full h-1 h-full transform bg-gray-900" x-transition:enter="transition ease duration-200" x-transition:enter-start="scale-0" x-transition:enter-end="scale-100" x-transition:leave="transition ease-out duration-300" x-transition:leave-start="scale-100" x-transition:leave-end="scale-0"></span>
                    </span>
                </a>
            </nav>
    
            <div class="relative z-10 inline-flex items-center space-x-3 md:ml-5 lg:justify-end">
                <!--<a href="#" class="inline-flex items-center justify-center px-4 py-2 text-base font-medium leading-6 text-gray-600 whitespace-no-wrap bg-white border border-gray-200 rounded-md shadow-sm hover:bg-gray-50 focus:outline-none focus:shadow-none">
                    Sign in
                </a>-->
                <span class="inline-flex rounded-md shadow-sm">
                    <a href="#" class="inline-flex items-center justify-center px-4 py-2 text-base font-medium leading-6 text-white whitespace-no-wrap bg-blue-600 border border-blue-700 rounded-md shadow-sm hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
                      🔜 Track your progress
                    </a>
                </span>
            </div>
        </div>
    </header>
    
    <section class="w-full px-6 mb-12 antialiased bg-white select-none">
      <div class="mx-auto max-w-7xl">
          <div class="container max-w-lg px-4 py-32 mx-auto text-left md:max-w-none md:text-center">
  
              <h1 class="text-5xl font-extrabold tracking-tight text-left text-gray-900 leading-tightest md:leading-10 md:text-center sm:leading-none md:text-6xl lg:text-7xl"><span class="inline md:block" id="">Learn A New Technology</span> <span class="relative mt-2 text-transparent md:inline-block bg-clip-text bg-gradient-to-br from-purple-600 to-blue-700" id="">&amp; Grow Yourself</span></h1>
              <div class="mx-auto mt-5 text-gray-500 md:mt-12 md:max-w-lg md:text-center lg:text-lg" id="">Choose from 12+ upcoming technologies. Learn for free. Absolutely no charges!</div>
              <div class="flex flex-col items-center mt-12 text-center">
                  <span class="relative inline-flex w-full rounded-full shadow-sm md:w-auto">
                      <button type="button" class="inline-flex items-center justify-center w-full px-8 py-4 text-base font-bold leading-6 text-white transition duration-150 ease-in-out bg-blue-600 border border-transparent rounded-full md:w-auto hover:bg-blue-700 focus:outline-none focus:border-blue-700 focus:shadow-outline-blue active:bg-blue-700" id=""><a href="#categories">Browse The Categories</a></button>
                      <span class="absolute top-0 right-0 px-2 py-1 -mt-3 -mr-6 text-xs font-medium leading-tight text-white bg-green-400 rounded-full" id="">Free</span>
                  </span>
                  <a href="#footer" class="capitalize font-semibold mt-3 text-sm text-blue-700" id="">or get the whole resource</a>
              </div>
          </div>
      </div>
  </section>
    
    <!--      
    <div class="font-inter flex flex-grow pt-4 justify-center items-center">
      <div class="text-center">
        <a href="/">
        <img src={logo} alt="Logo" />
        </a>
      </div>
    </div>
      <div class="font-inter flex flex-grow h-auto py-4 justify-center items-center">
      <div class="textBox text-center">
        <p class="text-lg">
          <strong>LearningIn.Tech is an <a class="text-blue-700" href="https://github.com/dwivedithedev/LIT">Open-source</a> stack of 100+ resources to learn new technologies for beginners. 
            <br/>All of the resources listed here handpicked & curated by humans.</strong>
        </p>
      </div>
    </div -->
    
    <section id='categories' class="px-2 py-5 bg-white md:px-0">
      <div class="container items-center max-w-6xl px-5 mx-auto space-y-6 text-center">
          <h1 class="text-4xl font-extrabold tracking-tight text-left text-gray-900 sm:text-5xl md:text-6xl md:text-center">
              <span class="block">Level Up with <span class="block mt-1 text-blue-700 lg:inline lg:mt-0">New Tech.</span></span>
          </h1>
          <p class="w-full mx-auto text-base text-left text-gray-500 md:max-w-md sm:text-lg lg:text-2xl md:max-w-3xl md:text-center" id="">
              Improve your soft skills & shine in your <i>Resume</i>!
          </p>
      </div>
  </section>  
    <!-- Row ONE of 4 Categories-->
      <div class="cards-list px-5">
      
            <div class="card 1">
                <div class="card_image"> 
                  <Router>
                  <a href="/AugmentedReality">
                    <img src="https://i.imgur.com/VzDSH6Z.jpg" /> 
                  </a>
                </Router>
                </div>
                <div class="card_title text-blue-600">
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
                <div class="card_title text-blue-600">
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
                <div class="card_title text-blue-600">
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
                <div class="card_title text-blue-600">
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
          <div class="card_title text-blue-600">
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
          <div class="card_title text-blue-600">
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
          <div class="card_title text-blue-600">
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
          <div class="card_title text-blue-600">
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
          <div class="card_title text-blue-600">
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
          <div class="card_title text-blue-600">
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
          <div class="card_title text-blue-600">
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
          <div class="card_title text-blue-600">
            <a href="/Voice">
            <p>Voice</p>
          </a>
          </div>
        </div>
      </div>

      <!--<div class="font-inter flex flex-grow h-screen px-10 justify-center items-center">
        <div class="text-center">
          <p class="sm:text-5xl md:text-5xl lg:text-5xl xl:text-5xl font-bold text-blue-400">Learn with the #LITCommunity</p>
          <p class="sm:text-xl md:text-xl lg:text-2xl xl:text-2xl font-bold mt-4 mx-4">
            Meet, Share and Chill with other amazing learners from around the world.
          </p>
          <div class="mt-4">
          <button class="shiny-btn"><a href="https://discord.gg/A2jejy2"><img src="https://discord.com/assets/e7a3b51fdac2aa5ec71975d257d5c405.png" width="128px" height="64px" /></a></button>
          </div>
        </div>
      </div>-->
    
    
      <div id="footer">
      <Footer/>
      </div>
    </div>