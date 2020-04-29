<script>
import { currentRoute, Link } from 'svelte-grouter';
import About from './About.svelte';
import Gallery from './Gallery.svelte';
import Projects from './Projects.svelte';
import Notes from './Notes.svelte';

const routes = {
	about: {
		path: '/about',
		component: About,
	},
	gallery: {
		path: '/gallery',
		component: Gallery,
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

const navItems = [
	{ label: "About", route: routes.about, path: "/about" },
	{ label: "Gallery", route: routes.gallery, path: "/gallery" },
	{ label: "Projects", route: routes.projects, path: "/projects" },
	{ label: "Notes", route: routes.notes, path: "/notes" },
];
let displayedNavItems = [];

export let visible;

$: visible = $currentRoute.path !== "/";
$: displayedNavItems = [...navItems].filter((nav) => nav.path !== $currentRoute.path);

</script>

{#if visible}
<nav class="navBar">
	<div>
		<ul>
		{#each displayedNavItems as item}
			<li>
				<Link route={item.route}>{item.label}</Link>
			</li>
		{/each}
		</ul>
	</div>
</nav>
{/if}

<style>

	.navBar {
		height: 5vh;
		width: 100vw;
		background-color: #282423;
	}

	ul {
		height: 5vh;
		display: flex;
		justify-content: flex-end;
		align-items: center;
		margin: 0;
	}

	nav :global(a) {
		text-decoration: none;
		/* display: block;
		text-align: center; */
		/* padding: 1vh 1vw; */
		font-size: 1em;
		color: gray
	}

	li {
		list-style-type: none;
		margin: 0 2vw;
	}

	nav :global(a):hover {
		/* background-color: black; */
		color: white;
	}


</style>