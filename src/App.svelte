<script>
  import { GRouter } from "svelte-grouter";

  import Gallery from './Gallery.svelte';
  import Home from './Home.svelte';
  import Navbar from './Navbar.svelte';
  import About from './About.svelte';
  import Projects from './Projects.svelte';
  import Notes from './Notes.svelte';

  const routes = {
  	home: {
  		path: '/',
  		component: Home,
  	},
  	gallery: {
  		path: '/gallery',
  		component: Gallery,
  	},
  	about: {
  		path: '/about',
  		component: About,
  	},
  	projects: {
  		path: '/projects',
  		component: Projects,
  	},
  	notes: {
  		path: '/notes',
  		component: Notes,
  	}
    
  };
  
  </script>

    <div>
      <Navbar />
      <GRouter {routes} />
    </div>