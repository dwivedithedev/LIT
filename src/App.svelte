<script>

/*
This is the place where you are supposed to write all the routes. 
It will work as intended.

The main.js loads the App.svelte where Home component by default because it is on "/" route.

*/
      import { Router, Link, Route } from "svelte-routing";

      import Home from './Home.svelte';
      import Tracker from './Tracker.svelte';
      import About from './About.svelte';
      import AugmentedReality from './AugmentedReality.svelte';
      import VirtualReality from './VirtualReality.svelte';
      import GameDevelopment from './GameDevelopment.svelte';
      import InternetofThings from './InternetofThings.svelte';
      import MachineLearning from './MachineLearning.svelte';
      import DeepLearning from './DeepLearning.svelte';
      import ArtificialIntelligence from './ArtificialIntelligence.svelte';
      import BigData from './BigData.svelte';
      import DataScience from './DataScience.svelte';
      import Blockchain from './Blockchain.svelte';
      import Automation from './Automation.svelte';
      import Voice from './Voice.svelte';
      import Footer from './Footer.svelte';
      
    export let url = "";
</script>

<Router>
  <div>
    <Route path="/" component="{Home}" />
    <Route path="/tracker" component="{Tracker}" />
    <Route path="/AugmentedReality" component="{AugmentedReality}" />
    <Route path="/About" component="{About}" />
    <Route path="/VirtualReality" component="{VirtualReality}" />
    <Route path="/GameDevelopment" component="{GameDevelopment}" />
    <Route path="/InternetofThings" component="{InternetofThings}" />
    <Route path="/MachineLearning" component="{MachineLearning}" />
    <Route path="/DeepLearning" component="{DeepLearning}" />
    <Route path="/ArtificialIntelligence" component="{ArtificialIntelligence}" />
    <Route path="/BigData" component="{BigData}" />
    <Route path="/DataScience" component="{DataScience}" />
    <Route path="/Blockchain" component="{Blockchain}" />
    <Route path="/Automation" component="{Automation}" />
    <Route path="/Voice" component="{Voice}" />
  </div>
</Router>