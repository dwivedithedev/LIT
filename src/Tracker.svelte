<svelte:head>
  <base target="_blank"/>
  <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</svelte:head>
<style>
    .float-btn {
        top: 10px;
        right:0;
        position:fixed;
        cursor:copy;
    }
    .twitter-timeline {
    max-width: 100%;
    max-height: 1000px;
    }
    .fa {
    font-size: 25px;
    color: #FFFFFF;
    }
    .panel-title {
    font-size: 25px; 
    color: #FFFFFF;
    font-family: 'Open Sans', sans-serif;
    }
    .panel-heading {
    background-color: #1da1f2 !important;
    color: #1da1f2 !important;
    }
    .panel {
    margin-top: 25px;
}
</style>
<script>
    import {onMount} from 'svelte';
    import Footer from './Footer.svelte';

    let yes = false;
    let day,tweetcontent;

    let username = localStorage.getItem('username');

    let src = `http://www.twitter.com/${username}`
    let twitterLink = `https://twitter.com/intent/tweet?text=`

    function updateUsername(){
    localStorage.setItem('username', username);
    location.reload();
    }

    function tweetProgress(){

        day = document.getElementById('day').value
        tweetcontent = document.getElementById('tweetcontent').value

        
        let finaltweet = 
        `Day ${day} / 100 :- ${tweetcontent} %23100DaysofCode %23DevCommunity %23LITCommunity`

        console.log('progress logged!')
        addToTimeline(day)
        window.open(twitterLink+finaltweet, '_blank');

    }

    function addToTimeline(day){
        //This will add the entry to HTML list
        let d = new Date();
        let ele = `<li class="relative -mb-px block border p-4 border-grey"><span class='font-semibold'>Day ${day}</span> completed! 🎉</li>`
        document.getElementById('userTimeline').innerHTML += ele

        //add to timeline
        let t = localStorage.getItem('usertimeline');
        let timeline = JSON.parse(t);
        console.log(typeof(timeline))
        timeline.push(day)
        let newTimeline = JSON.stringify(timeline)
        localStorage.setItem('usertimeline',newTimeline)
    }

    function bookmark(title, href) {
    if (window.sidebar && window.sidebar.addPanel) { // Mozilla Firefox Bookmark
        window.sidebar.addPanel(title,href,'');
    } else if(window.external && ('AddFavorite' in window.external)) { // IE Favorite
        window.external.AddFavorite(href,title); 
    } else if(window.opera && window.print) { // Opera Hotlist
        this.title=title;
        return true;
    } else { // webkit - safari/chrome
        alert('Press ' + (navigator.userAgent.toLowerCase().indexOf('mac') != - 1 ? 'Command/Cmd' : 'CTRL') + ' + D to bookmark this page.');
    }
}

    onMount(()=>{
        let i;

        if(localStorage.getItem('usertimeline') !== null)
        {
            let t = localStorage.getItem('usertimeline');
            let timeline = JSON.parse(t)
            for(i=0;i<timeline.length;i++)
            {
                let ele = `<li class="relative -mb-px block border p-4 border-grey"><span class='font-semibold'>Day ${timeline[i]} Completed</span></li>`
                document.getElementById('userTimeline').innerHTML += ele
            }
        }
        else {  let val=[]
                localStorage.setItem('usertimeline',JSON.stringify(val))
            }
    });
</script>
<div>
    <header class="w-full px-3 antialiased bg-blue-700 select-none lg:px-6">
        <div class="mx-auto max-w-7xl">
            <div class="container pt-16 pb-5 mx-auto text-center sm:px-4">
                <span class="text-xl font-extrabold leading-10 tracking-tight text-white sm:text-6xl sm:leading-none md:text-6xl xl:text-6xl"><span class="block">Track Your Progress</span> <span class="relative inline-block mt-3 text-transparent text-white">#100DaysofCode</span></span>
                <div class="max-w-lg mx-auto mt-2 text-sm text-center text-indigo-200 md:mt-12 sm:text-base md:max-w-xl md:text-lg xl:text-xl">Replace with your username & use this dashboard to track, update & maintain your progress of #100DaysofCode!</div>
                
            <div class="my-4">
                <div class="pb-6 md:pb-0 flex flex-col">
                    <div>
                        <label class="input-field inline-flex items-baseline border-none shadow-md bg-white p-4">
                            <span class="flex-none text-dusty-blue-darker select-none leading-none">twitter.com/</span>
                            <div class="flex-1 leading-none">
                                <input bind:value={username} id="handle" type="text" class="placeholder-blue w-full p-0 outline-none text-dusty-blue-darker" name="handle" placeholder="username">
                            </div>
                            <button class='text-blue-500 font-semibold outline-none' on:click={updateUsername}>Apply</button>
                        </label>
                    </div>
                </div>
                <div><div class='text-md m-4 font-semibold text-white'>Powered by <a href='http://learningin.tech/'>LearningInTech</a></div></div>
            </div>
            
            </div>
        </div>
    </header>    
    <div class="flex flex-wrap overflow-hidden">

        <div class="xl:w-2/4 md:w-2/4 lg:w-2/4 sm:w-full w-full h-screen overflow-hidden border-gray-300">
          <!-- Column Content -->
        <div class='container'>
            <div>
                <section class="px-2 py-5 bg-white md:px-0">
                    <div class="container items-center max-w-6xl px-5 mx-auto space-y-6">
                        <h1 class="text-center text-2xl font-extrabold tracking-tight text-gray-900 sm:text-2xl md:text-3xl md:text-center">
                            <span class="block">Tweet Your Progress<span class="text-blue-700">.</span></span>
                        </h1>
                        <p class="w-full mx-auto text-gray-500 sm:text-lg lg:text-xl md:text-center">
                            Use the form below to tweet your today's progress.
                        </p>
                        <div class="mx-auto px-10 divide-y divide-gray-200">
                        <form action='#' on:submit|preventDefault={tweetProgress}>
                            <div class="py-8 text-base leading-6 space-y-4 text-gray-700 sm:text-lg sm:leading-7">
                                <div class="flex flex-col">
                                    <label class="leading-loose">Enter the day of code</label>
                                    <input id='day' type="number" class="px-4 py-2 border focus:ring-gray-500 focus:border-blue-700 w-full sm:text-sm border-gray-300 rounded-md focus:outline-none text-gray-600" placeholder="10" required>
                                </div>
                                <div class="flex flex-col">
                                    <label class="leading-loose">Write about your work progress</label>
                                    <textarea id='tweetcontent' class="description sec p-3 h-60 border focus:border-blue-700 border-gray-300 rounded-md focus:outline-none" spellcheck="false" placeholder="Describe everything what you worked on today or your small wins you want to share / log." required></textarea>
                                        <!-- icons -->
                                        <div class="icons flex text-gray-500 m-2">
                                        <div class="count ml-auto text-gray-400 text-xs font-semibold">max. 250 characters.</div>
                                        </div>
                                    </div>
                                <div class="flex flex-col">
                                    <label class="text-center">
                                        <div class="text-base text-blue-700 ">Hashtags related to #100DaysofCode will be added automatically to your progress tweet.</div>
                                    </label>
                                </div>
                            </div>
                            <div class="pt-2 flex items-center space-x-4">
                                <button class="bg-blue-700 flex justify-center items-center w-full text-white px-4 py-3 rounded-md font-semibold focus:outline-none" type="submit">Tweet my progress</button>
                            </div>
                        </form>
                    </div>
                </section>
            </div>
        </div>
        </div>

        <div class="xl:w-1/4 md:w-1/4 lg:w-1/4 sm:w-full w-full h-auto overflow-hidden border-gray-300 border-2">
            <!-- Column Content -->
            <h1 class="py-2 text-center text-2xl font-extrabold tracking-tight text-gray-900 sm:text-2xl md:text-3xl md:text-center">
                <span class="block">Your Timeline<span class="text-blue-700">.</span></span>
            </h1>
            <ul id='userTimeline' class=" list-reset flex flex-col">
            </ul>
          </div>

          <div class="xl:w-1/4 md:w-1/4 lg:w-1/4 sm:w-full w-full h-auto overflow-hidden border-gray-300 border-2">
            <!-- Column Content -->
            <h1 class="py-2 text-center text-2xl font-extrabold tracking-tight text-gray-900 sm:text-2xl md:text-3xl md:text-center">
                <span class="block">Your Tweets<span class="text-blue-700">.</span></span>
            </h1>
            <a class="twitter-timeline" href={src}>Tweets by {username}</a>
          </div>
          <span on:click={bookmark} class="float-btn bg-blue-500 rounded-full font-bold text-white px-4 py-3 transition duration-300 ease-in-out hover:bg-blue-600 mr-6">
            Bookmark this!
          </span>
    </div>
    <div id="footer">
        <Footer/>
    </div>
</div>