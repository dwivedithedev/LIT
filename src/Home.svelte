<svelte:head>
    <script src="https://gumroad.com/js/gumroad.js"></script>
</svelte:head>
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
      box-shadow: 2px 2px 15px 4px rgba(0,0,0,0.25), -2px -2px 15px 4px rgba(0,0,0,0.22);
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
                <a href="/ArtificialIntelligence" class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900">
                    <span class="block">AI</span>
                    <span class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden">
                        <span x-show="hover" class="absolute inset-0 inline-block w-full h-full transform bg-gray-900" x-transition:enter="transition ease duration-200" x-transition:enter-start="scale-0" x-transition:enter-end="scale-100" x-transition:leave="transition ease-out duration-300" x-transition:leave-start="scale-100" x-transition:leave-end="scale-0"></span>
                    </span>
                </a>
                <a href="/MachineLearning" class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900">
                    <span class="block">ML</span>
                    <span class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden">
                        <span x-show="hover" class="absolute inset-0 inline-block w-full h-full transform bg-gray-900" x-transition:enter="transition ease duration-200" x-transition:enter-start="scale-0" x-transition:enter-end="scale-100" x-transition:leave="transition ease-out duration-300" x-transition:leave-start="scale-100" x-transition:leave-end="scale-0"></span>
                    </span>
                </a>
                <a href="/AugmentedReality" class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900">
                    <span class="block">AR</span>
                    <span class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden">
                        <span x-show="hover" class="absolute inset-0 inline-block w-full h-full transform bg-gray-900" x-transition:enter="transition ease duration-200" x-transition:enter-start="scale-0" x-transition:enter-end="scale-100" x-transition:leave="transition ease-out duration-300" x-transition:leave-start="scale-100" x-transition:leave-end="scale-0"></span>
                    </span>
                </a>
                <a href="/VirtualReality" class="relative font-medium leading-6 text-gray-600 transition duration-150 ease-out hover:text-gray-900">
                    <span class="block">VR</span>
                    <span class="absolute bottom-0 left-0 inline-block w-full h-0.5 -mb-1 overflow-hidden">
                        <span x-show="hover" class="absolute inset-0 inline-block w-full h-full transform bg-gray-900" x-transition:enter="transition ease duration-200" x-transition:enter-start="scale-0" x-transition:enter-end="scale-100" x-transition:leave="transition ease-out duration-300" x-transition:leave-start="scale-100" x-transition:leave-end="scale-0"></span>
                    </span>
                </a>
            </nav>
    
            <div class="relative z-10 inline-flex items-center space-x-3 md:ml-5 lg:justify-end">
                <!--<a href="#" class="inline-flex items-center justify-center px-4 py-2 text-base font-medium leading-6 text-gray-600 whitespace-no-wrap bg-white border border-gray-200 rounded-md shadow-sm hover:bg-gray-50 focus:outline-none focus:shadow-none">
                    Sign in
                </a>-->
                <span class="inline-flex rounded-md shadow-sm">
                  <a href="https://gum.co/learningkit" target="_blank" class="gumroad-button inline-flex items-center justify-center px-5 py-3 text-base font-medium text-blue-700 bg-indigo-100 border border-transparent rounded-md hover:bg-indigo-200" id="">
                    Get Learning Kit
                  </a>
                    <!-- <a href="/tracker" class="inline-flex items-center justify-center px-4 py-2 text-base font-medium leading-6 text-white whitespace-no-wrap bg-blue-600 border border-blue-700 rounded-md shadow-sm hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
                      🆕 Track your progress
                    </a> -->
                </span>
            </div>
        </div>
    </header>
    
    <section class="w-full px-6 mb-12 antialiased bg-white select-none">
      <div class="mx-auto max-w-7xl">
          <div class="container max-w-lg px-4 py-32 mx-auto text-left md:max-w-none md:text-center">
  
              <h1 class="text-5xl font-extrabold tracking-tight text-left text-gray-900 leading-tightest md:leading-10 md:text-center sm:leading-none md:text-6xl lg:text-7xl"><span class="inline md:block" id="">Learn A New Technology</span> <span class="relative mt-2 text-transparent md:inline-block bg-clip-text bg-gradient-to-br from-purple-600 to-blue-700" id="">&amp; Grow Yourself</span></h1>
              <div class="mx-auto mt-5 font-semibold text-gray-700 md:mt-12 md:max-w-lg md:text-center lg:text-lg" id="">Browse from 12+ technologies. Start your <a href='/tracker' class="text-blue-400">#100DaysofCode.</a></div>
              <div class="flex flex-col items-center mt-12 text-center">
                  <span class="relative inline-flex w-full rounded-full shadow-sm md:w-auto">
                      <button type="button" class="inline-flex items-center justify-center w-full px-8 py-4 text-base font-bold leading-6 text-white transition duration-150 ease-in-out bg-blue-600 border border-transparent rounded-md md:w-auto hover:bg-blue-700 focus:outline-none focus:border-blue-700 focus:shadow-outline-blue active:bg-blue-700" id=""><a href="#categories">Browse The Categories</a></button>
                      <span class="absolute top-0 right-0 px-2 py-1 -mt-3 -mr-6 text-xs font-medium leading-tight text-white bg-green-400 rounded-full" id="">Updated</span>
                  </span>
                  <a href="/tracker" target="_blank" class="capitalize font-semibold mt-3 text-sm text-blue-700" id=""></a>
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
          <p class="w-full mx-auto text-base text-left font-semibold text-gray-700 sm:text-lg lg:text-2xl md:max-w-3xl md:text-center" id="">
              Improve your soft skills & shine in your <i>Resume</i>!
          </p>
      </div>
  </section>  

    <!-- Row ONE of 4 Categories-->
    <div class="cards-list px-20">
      
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
<div class="cards-list px-20">

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
<div class="cards-list px-20">

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

<section class="pt-10 text-gray-600 body-font">
  <div class="container items-center mt-10 max-w-6xl px-5 mx-auto space-y-6 text-center">
    <h1 class="text-3xl font-extrabold tracking-tight text-left text-gray-900 sm:text-5xl md:text-6xl md:text-center">
        <span class="block">How to get started <span class="block mt-1 text-blue-700 lg:inline lg:mt-0">learning?</span></span>
    </h1>
  </div>
  <div class="container px-5 py-20 mx-auto flex flex-wrap">
    <div class="flex relative pt-10 pb-20 sm:items-center md:w-2/3 mx-auto">
      <div class="h-full w-6 absolute inset-0 flex items-center justify-center">
        <div class="h-full w-1 bg-gray-200 pointer-events-none"></div>
      </div>
      <div class="flex-shrink-0 w-6 h-6 rounded-full mt-10 sm:mt-0 inline-flex items-center justify-center bg-blue-500 text-white relative z-10 title-font font-medium text-sm">1</div>
      <div class="flex-grow md:pl-8 pl-6 flex sm:items-center items-start flex-col sm:flex-row">
        <div class="flex-shrink-0 w-24 h-24 bg-blue-100 text-blue-500 rounded-full inline-flex items-center justify-center">
          <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1" class="w-12 h-12" viewBox="0 0 24 24">
            <path d="M3 3h18a1 1 0 0 1 1 1v16a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V4a1 1 0 0 1 1-1zm1 2v14h16V5H4zm8 10h6v2h-6v-2zm-3.333-3L5.838 9.172l1.415-1.415L11.495 12l-4.242 4.243-1.415-1.415L8.667 12z" fill="rgba(63,131,248,1)"/>
          </svg>
        </div>
        <div class="flex-grow sm:pl-6 mt-6 sm:mt-0">
          <h2 class="font-medium title-font text-gray-900 mb-1 text-xl">Pick a Technology!</h2>
          <p class="leading-relaxed">Browse from the categories & choose the one you want to learn. <br/>(OR the one which excites you the most.)</p>
        </div>
      </div>
    </div>
    <div class="flex relative pb-20 sm:items-center md:w-2/3 mx-auto">
      <div class="h-full w-6 absolute inset-0 flex items-center justify-center">
        <div class="h-full w-1 bg-gray-200 pointer-events-none"></div>
      </div>
      <div class="flex-shrink-0 w-6 h-6 rounded-full mt-10 sm:mt-0 inline-flex items-center justify-center bg-blue-500 text-white relative z-10 title-font font-medium text-sm">2</div>
      <div class="flex-grow md:pl-8 pl-6 flex sm:items-center items-start flex-col sm:flex-row">
        <div class="flex-shrink-0 w-24 h-24 bg-blue-100 text-blue-500 rounded-full inline-flex items-center justify-center">
          <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1" class="w-12 h-12" viewBox="0 0 24 24">
            <path d="M6 19h12V9.157l-6-5.454-6 5.454V19zm13 2H5a1 1 0 0 1-1-1v-9H1l10.327-9.388a1 1 0 0 1 1.346 0L23 11h-3v9a1 1 0 0 1-1 1zM7.5 13h2a2.5 2.5 0 1 0 5 0h2a4.5 4.5 0 1 1-9 0z" fill="rgba(50,152,219,1)"/>  
          </svg>
        </div>
        <div class="flex-grow sm:pl-6 mt-6 sm:mt-0">
          <h2 class="font-medium title-font text-gray-900 mb-1 text-xl">Setup your <a href='/tracker' class='text-blue-500 font-bold'>Tracker</a></h2>
          <p class="leading-relaxed">LIT provides you with a <a href='/tracker' class="text-blue-500 font-bold" target='blank'>Tracker</a> which you can use to log your progress. Replace with your username & maintain your progress with #100DaysofCode!</p>
        </div>
      </div>
    </div>
    <div class="flex relative pb-20 sm:items-center md:w-2/3 mx-auto">
      <div class="h-full w-6 absolute inset-0 flex items-center justify-center">
        <div class="h-full w-1 bg-gray-200 pointer-events-none"></div>
      </div>
      <div class="flex-shrink-0 w-6 h-6 rounded-full mt-10 sm:mt-0 inline-flex items-center justify-center bg-blue-500 text-white relative z-10 title-font font-medium text-sm">3</div>
      <div class="flex-grow md:pl-8 pl-6 flex sm:items-center items-start flex-col sm:flex-row">
        <div class="flex-shrink-0 w-24 h-24 bg-blue-100 text-blue-500 rounded-full inline-flex items-center justify-center">
          <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1" class="w-12 h-12" viewBox="0 0 24 24">
            <path d="M12 14v2a6 6 0 0 0-6 6H4a8 8 0 0 1 8-8zm0-1c-3.315 0-6-2.685-6-6s2.685-6 6-6 6 2.685 6 6-2.685 6-6 6zm0-2c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm6 10.5l-2.939 1.545.561-3.272-2.377-2.318 3.286-.478L18 14l1.47 2.977 3.285.478-2.377 2.318.56 3.272L18 21.5z" fill="rgba(50,152,219,1)"/>
          </svg>
        </div>
        <div class="flex-grow sm:pl-6 mt-6 sm:mt-0">
          <h2 class="font-medium title-font text-gray-900 mb-1 text-xl">Start your Learning!</h2>
          <p class="leading-relaxed">Bookmark both the page of category you picked & the tracker dashboard. Start learning from mentioned resources & log daily progress with Tracker. All the best!</p>
        </div>
      </div>
    </div>
  </div>
</section>


<div class="px-4 py-16 mx-auto sm:max-w-xl md:max-w-full lg:max-w-screen-xl md:px-24 lg:px-8 lg:py-20">
  <div class="grid row-gap-8 sm:grid-cols-3">
    <div class="text-center">
      <h6 class="text-5xl font-bold text-blue-700">150+</h6>
      <p class="font-bold">Resources</p>
    </div>
    <div class="text-center">
      <h6 class="text-5xl font-bold text-blue-700">12+</h6>
      <p class="font-bold">Technologies</p>
    </div>
    <div class="text-center">
      <h6 class="text-5xl font-bold text-blue-700">250+</h6>
      <p class="font-bold">Hours of Research</p>
    </div>
  </div>
</div>


      <section class="text-gray-600 body-font">
        <div class="container px-5 py-24 mx-auto flex flex-wrap">
          <h2 class="text-5xl text-gray-900 font-extrabold tracking-tight leading-tightest text-left sm:leading-none title-font mb-2 md:w-2/5">Why LearningInTech?</h2>
          <!-- <h1 class="text-5xl font-extrabold tracking-tight text-left text-gray-900 leading-tightest md:leading-10 md:text-center sm:leading-none md:text-6xl lg:text-7xl"><span class="inline md:block" id="">Learn A New Technology</span> <span class="relative mt-2 text-transparent md:inline-block bg-clip-text bg-gradient-to-br from-purple-600 to-blue-700" id="">&amp; Grow Yourself</span></h1> -->
          
          <div class="md:w-3/5 md:pl-32">
            <p class="leading-relaxed text-base font-semibold text-gray-700">
              This resource is a by-product of research work done when I was exploring new technologies. I used to try every resource & bookmark those which were practical & easy to learn.
              It took me more than 250+ hours of research to curate them. <br/>
              I hope this can save you time & help you start your journey in tech. :)
            </p>
            <!-- <div class="flex md:mt-4 mt-6">
              <a class="text-blue-500 inline-flex items-center ml-4">Learn More
                <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-4 h-4 ml-2" viewBox="0 0 24 24">
                  <path d="M5 12h14M12 5l7 7-7 7"></path>
                </svg>
              </a>
            </div> -->
          </div>
        </div>
      </section>
    
      <div id="footer">
      <Footer/>
      </div>
    </div>