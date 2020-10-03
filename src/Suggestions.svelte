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
    import ShareSubmit from './ShareSubmit.svelte';
    import {link} from 'svelte-routing';
    import { onMount } from 'svelte';

    import loader from './loader.svg';

</script>
<div>
    <!-- Header Component-->
    <div class="font-inter flex flex-grow h-auto justify-center items-center py-10">
        <div class="text-center">
            <a href="/"><p class="text-5xl font-bold text-blue-400">Learning in Tech</p></a>
          <p class="text-3xl mt-2">
            <strong>Suggest a Resource</strong>
          </p>
          <p class="textBox text-lg mt-2 m-5">
            Do you think you have an awesome resource or tutorial which can fall into one of the given categories? Let me know here. Thank you.
          </p>
        </div>
    </div>

    <!-- Show the embedded form here-->
      <div class="textBox text-center">
        <div class="typeform-widget" data-url="https://form.typeform.com/to/kMMVYmum" data-transparency="50" data-hide-headers="true" data-hide-footer="true" style="width: 100%; height: 300px;"></div> <script> (function() { var qs,js,q,s,d=document, gi=d.getElementById, ce=d.createElement, gt=d.getElementsByTagName, id="typef_orm", b="https://embed.typeform.com/"; if(!gi.call(d,id)) { js=ce.call(d,"script"); js.id=id; js.src=b+"embed.js"; q=gt.call(d,"script")[0]; q.parentNode.insertBefore(js,q) } })() </script> 
      </div>
  
  <div class="p-50">
    <Footer/>
  </div>
</div>