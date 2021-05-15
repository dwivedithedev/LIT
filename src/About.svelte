<svelte:head>
  <base target="_blank"/>
</svelte:head>
<style>
  .textBox{
    padding: 20px;
    
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
    import logo from './img/logo.png';
    import ShareSubmit from './ShareSubmit.svelte';
    import {link} from 'svelte-routing';
    import { onMount } from 'svelte';

    import loader from './loader.svg';

</script>
<div>
	<!-- Header Component-->
	
    <div class="font-inter flex flex-grow pt-4 justify-center items-center">
		<div class="text-center">
		  <a href="/">
		  <img src={logo} alt="Logo" />
		  <h1 class="text-2xl resize font-bold text-blue-400">Learning in Tech</h1>
		  </a>
		</div>
	  </div>

    <div class="font-inter flex flex-grow h-auto justify-center items-center py-10">
        <div class="text-center">
          <p class="text-3xl mt-2">
            <strong>About the Mission</strong>
          </p>
          <p class="textBox font-normal max-w-xl text-justify text-2xl mt-2 m-5">
			LearningIn.Tech is an open source project made for and by learners in the world of technology whose aim is to build a resource of the best, high quality and free resources to learn new technologies. 
			All of the resources listed here handpicked & curated by humans. 
			<br/><br/>You can also contribute and support the open source project. 
			<br/><br/>Thank you <span role="img">💙</span>.
		  </p>
		<button
		type="button"
		class="border border-blue-500 text-blue-500 rounded-md px-4 py-2 m-2 transition duration-500 ease select-none hover:text-white hover:bg-blue-500 focus:outline-none focus:shadow-outline"
	  >
	  <a href="https://dev.to/thevediwho/how-to-start-contributing-in-open-source-with-learningin-tech-5acn" target="_blank">Contribute to Learningin.tech</a>
	  </button>
		</div>
	</div>
  <div class="p-50">
    <Footer/>
  </div>
</div>