<script>
  import { Router, Route } from "svelte-routing";

	import Nested from './Nested.svelte';
  import Home from './Home.svelte';

	export let name;
	name = '<h2>Valera</h2>';
  
  export let url = "";

  </script>
    <Router url="{url}">
      <div>
        <Route path="/"><Home /></Route>
        <Route path="about" component={Nested} />
      </div>
    </Router>