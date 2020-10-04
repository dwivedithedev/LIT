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
        setTimeout(clearStorageUpdateContent,300000);
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
                  <Link to="/AugmentedReality">
                    <img src="https://i.imgur.com/VzDSH6Z.jpg" /> 
                  </Link>
                </Router>
                </div>
                <div class="card_title text-blue-500">
                  <Link to="/AugmentedReality">
                    <p>Augmented Reality</p>
                  </Link>
                </div>
            </div>
        
            <div class="card 1">
                <div class="card_image"> 
                  <Link to="/VirtualReality">
                    <img src="https://i.imgur.com/29SYpw0.png" /> 
                  </Link>
                </div>
                <div class="card_title text-blue-500">
                    <Link to="/VirtualReality">
                    <p>Virtual Reality</p>
                </Link>
                </div>
            </div>
            
            <div class="card 1">
                <div class="card_image"> 
                  <Link to="/GameDevelopment">
                    <img src="https://i.imgur.com/vYQEgYx.png" /> 
                  </Link>
                </div>
                <div class="card_title text-blue-500">
                    <Link to="/GameDevelopment">
                    <p>Game Development</p>
                </Link>
                </div>
            </div>
    
            <div class="card 1">
                <div class="card_image"> 
                  <Link to="/InternetofThings">
                    <img src="https://i.imgur.com/s4ibcDU.jpg" /> 
                  </Link>
                </div>
                <div class="card_title text-blue-500">
                    <Link to="/InternetofThings">
                    <p>Internet of Things</p>
                </Link>
                </div>
            </div>
      </div>
    
      
    <!-- Row TWO of 4 Categories-->
      <div class="cards-list px-10">
      
        <div class="card 1">
          <div class="card_image"> 
            <Link to="/MachineLearning">
            <img src="https://i.imgur.com/lWk3GvR.jpg" />
            </Link>
          </div>
          <div class="card_title text-blue-500">
            <Link to="/MachineLearning">
            <p>Machine Learning</p>
            </Link>
          </div>
        </div>
        
        <div class="card 2">
          <div class="card_image">
            <Link to="/DeepLearning">
            <img src="https://i.imgur.com/1zydvP2.png" />
            </Link>
           </div>
          <div class="card_title text-blue-500">
            <Link to="/DeepLearning">
            <p>Deep Learning</p>
          </Link>
          </div>
        </div>
        
        <div class="card 3">
          <div class="card_image">
            <Link to="/ArtificialIntelligence">
            <img src="https://i.imgur.com/B0XxRQK.jpg" />
            </Link>
          </div>
          <div class="card_title text-blue-500">
            <Link to="/ArtificialIntelligence">
            <p>A.I.</p>
            </Link>
          </div>
        </div>
          
        <div class="card 4">
          <div class="card_image">
            <Link to="/Blockchain">
            <img src="https://i.imgur.com/zpEaAmU.png" />
            </Link>
            </div>
          <div class="card_title text-blue-500">
            <Link to="/Blockchain">
              <p>Blockchain</p>
            </Link>
          </div>
        </div>
    
      </div>
    
      <!-- Row THREE of 4 Categories-->
      <div class="cards-list px-10">
      
        <div class="card 1">
          <div class="card_image">
            <Link to="/BigData">
            <img src="https://i.imgur.com/28pCABK.png" /> 
            </Link>
          </div>
          <div class="card_title text-blue-500">
            <Link to="/BigData">
              <p>Big Data</p>
          </Link>
          </div>
        </div>
        
        <div class="card 2">
          <div class="card_image">
            <Link to="/DataScience">
            <img src="https://i.imgur.com/PfpJprq.png" />
            </Link>
            </div>
          <div class="card_title text-blue-500">
            <Link to="/DataScience">
            <p>Data Science</p>
          </Link>
          </div>
        </div>
        
        <div class="card 3">
          <div class="card_image">
            <Link to="/Automation">
            <img src="https://i.imgur.com/G96ou8Y.png" />
            </Link>
          </div>
          <div class="card_title text-blue-500">
            <Link to="/Automation">
            <p>Automation</p>
          </Link>
          </div>
        </div>
          
        <div class="card 4">
          <div class="card_image">
            <Link to="/Voice">
            <img src="https://i.imgur.com/VbbixtS.png" />
            </Link>
            </div>
          <div class="card_title text-blue-500">
            <Link to="/Voice">
            <p>Voice</p>
          </Link>
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