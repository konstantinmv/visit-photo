<script>
import { currentRoute, Link } from 'svelte-grouter';
import About from './About.svelte';
import Gallery from './Gallery.svelte';
import Projects from './Projects.svelte';
import Notes from './Notes.svelte';

import Icon from "fa-svelte";
import {
	faTelegramPlane,
	faLinkedinIn,
} from '@fortawesome/free-brands-svg-icons';
import {
	TELEGRAM_LINK,
	LINKEDIN_LINK,
} from '../static/constants';

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
const contactIcons = [
	{ href: TELEGRAM_LINK, icon: faTelegramPlane },
	{ href: LINKEDIN_LINK, icon: faLinkedinIn },
];
let displayedNavItems = [];

export let visible;

$: visible = $currentRoute.path !== "/";
$: displayedNavItems = [...navItems].filter((nav) => nav.path !== $currentRoute.path);

</script>

{#if visible}
<nav class="navBar">
	<div>
		<ul class="right">
			{#each contactIcons as icon}
				<a class="mediaIcon" href={icon.href}><Icon icon={icon.icon} /></a>
			{/each}
		</ul>
		<ul class="left">
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

	.left {
		height: 5vh;
		display: flex;
		justify-content: flex-end;
		align-items: center;
		margin: 0;
	}

	.right {
		margin: 0 auto;
		position: absolute;
		top: 2vh;
		width: 10vw;
	}

	.mediaIcon {
		padding: 0.5em;
		font-size: 1.5em;
	}

	nav :global(a) {
		text-decoration: none;
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