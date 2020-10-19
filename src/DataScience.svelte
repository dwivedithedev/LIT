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

    import loader from './loader.svg';
  
  let name="Data Science";
  
  let resources = [];
  let api = "https://api.apispreadsheets.com/data/1581/";

  let ass = [];
  let resBeginners = [];
  let resIntermediate = [];
  let resAdvanced = [];
  function filtering(){
    
    let filters=["Beginner","Intermediate","Advanced"]
    resBeginners = resources.filter( i => filters[0].includes( i.Type ) );
    resIntermediate = resources.filter( i => filters[1].includes( i.Type ) );
    resAdvanced = resources.filter( i => filters[2].includes( i.Type ) );
}

function apiCall(){
fetch(api).then(res=>{
 if (res.status === 200){
  let x = document.getElementById('loader');
  x = document.getElementById('loader');
  x.style.display = "none";
  // SUCCESS
  res.json().then(data=>{
    let yourData = data.data;
    ass = Object.values(yourData)
    localStorage.setItem("ecneicsatad", JSON.stringify(ass));
    resources = JSON.parse(localStorage.getItem("ecneicsatad"));

    //creating variables for filtering
    filtering()

    //console.log("localStorage created")
  }).catch(err => console.log(err))
}
else{
  // ERROR
  }
  })
  }

  onMount(()=>{
  console.log("onmount");
  let x = document.getElementById('loader');
  x.style.display = "block";

  if (localStorage.getItem("ecneicsatad") === null) {
  // we will make the API call and store it in localstorage.
  apiCall();
  }
  else {
    let x = document.getElementById('loader');
    x.style.display = "none";
    //console.log("localStorage already exists")
    resources = JSON.parse(localStorage.getItem("ecneicsatad"));

    //creating variables for filtering
    filtering()
  }

});

</script>
<div>
    <!-- Header Component-->
    <div class="font-inter flex flex-grow h-auto justify-center items-center py-10">
        <div class="text-center">
            <a href="/"><p class="text-5xl font-bold text-blue-400">Learning in Tech</p></a>
          <p class="text-3xl mt-2">
            <strong>{name}</strong>
          </p>
          <p class="textBox text-lg mt-2 m-5">
            <strong>{name}</strong> is an inter-disciplinary field that uses scientific methods, processes, algorithms and systems to extract knowledge and insights <br/> from many structural and unstructured data. Data science is related to data mining, machine learning and big data. <a class="text-blue-700" href="https://en.wikipedia.org/wiki/Data_science">(wiki.)</a><br/>
            Here is the list of top resources you can access to get started with {name}.
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
          <button class="bg-white hover:bg-gray-100 text-gray-800 font-semibold py-2 px-4 border border-gray-400 rounded shadow" on:click={()=>{ resources = JSON.parse(localStorage.getItem("ecneicsatad")); }}>
            All
          </button>
        </div>
    </div>

    <!-- Resources Component
    TODO:- THINK OF HOW TO DISPLAY RESOURCES, WHEN YOU ADD RESOURCES IN THIS AND FINALISE IT, THEN ONLY COPY PASTE THIS FOR OTHER CATEGORIES
    -->
    <div class="flex flex-grow justify-center items-center">
      <div class="text-center">
        <img id="loader" src={loader} />
      </div>
    </div>
   
    <div id="content">
    {#each resources as cat}
    <div class="flex bg-white shadow-lg rounded-lg mx-4 md:mx-auto mb-8 max-w-md md:max-w-2xl "><!--horizantil margin is just for display-->
      <div class="flex items-start px-4 py-6">
        <div class="">
            <div class="flex items-center justify-between">
              <small class="text-xs text-gray-900 -mt-1">{cat.Type}</small>
              <!--small class="text-sm text-gray-700">22h ago</small-->
            </div>
            <!--p class="text-gray-700">Joined 12 SEP 2012. </p-->
            <h2 class="mt-3 font-semibold text-blue-700 text-lg"><a href={cat.Link}>
              {cat.Name}
            </a></h2>
            <p>{cat.Description}</p>
        </div>
      </div>
    </div>
    {/each}
  </div>

  <!-- Add resource and share button-->
  <ShareSubmit/>
  <CTA category={name}/>
  <div class="p-50">
    <Footer/>
  </div>
</div>