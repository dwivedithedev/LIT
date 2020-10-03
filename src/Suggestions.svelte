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
	<a class="typeform-share button" href="https://form.typeform.com/to/kMMVYmum" data-mode="popup" style="display:inline-block;text-decoration:none;background-color:#3A7685;color:white;cursor:pointer;font-family:Helvetica,Arial,sans-serif;font-size:20px;line-height:50px;text-align:center;margin:0;height:50px;padding:0px 33px;border-radius:25px;max-width:100%;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;font-weight:bold;-webkit-font-smoothing:antialiased;-moz-osx-font-smoothing:grayscale;" target="_blank">Launch me </a> <script> (function() { var qs,js,q,s,d=document, gi=d.getElementById, ce=d.createElement, gt=d.getElementsByTagName, id="typef_orm_share", b="https://embed.typeform.com/"; if(!gi.call(d,id)){ js=ce.call(d,"script"); js.id=id; js.src=b+"embed.js"; q=gt.call(d,"script")[0]; q.parentNode.insertBefore(js,q) } })() </script>
  
  <div class="p-50">
    <Footer/>
  </div>
</div>