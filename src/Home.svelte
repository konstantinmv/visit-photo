	<script>
		import { navigateTo } from "svelte-grouter";
		import Gallery from './Gallery.svelte';
		import Icon from "fa-svelte";
		import {
			faInstagram,
			faTelegramPlane,
			faLinkedinIn,
		} from '@fortawesome/free-brands-svg-icons';
		import {
			INSTAGRAM_LINK,
			LINKEDIN_LINK,
			TELEGRAM_LINK,
		} from '../static/constants';

		const routes = {
			gallery: {
				path: '/gallery',
				component: Gallery,
			}
		};

		const goToGallery = () => {
			navigateTo(routes.gallery);
		};

	</script> 

	<div class="imageWelcome" style="background-image: url('images/entrance/000040.JPG')">
		<div class="infoDiv">
			<p class="homeText">Hello,</p>
			<div>
				<button class="enterButton" on:click={goToGallery}>
				Come on in
				</button>
			</div>
		</div>
		<div class="socialMediaDiv">
			<a class="mediaIcon" href={TELEGRAM_LINK}><Icon icon={faTelegramPlane} /></a>
			<a class="mediaIcon" href={LINKEDIN_LINK}><Icon icon={faLinkedinIn} /></a>
			<a class="mediaIcon" href={INSTAGRAM_LINK}><Icon icon={faInstagram} /></a>
		</div>
	</div>

	<style>

		.homeText {
			display: flex;
			color: white;
			font-size: 4em;
			margin: 0.5em;
			width: 15vw;
			justify-content: center;
		}

		.enterButton {
			background-color: transparent;
			border: 1px solid white;
			font-size: 2em;
			color: white;
		}

		.enterButton:hover {
			background-color: white;
			color: gray;
		}

		.socialMediaDiv {
			display: flex;
			flex-direction: column;
			position: absolute;
			top: 40vh; 
			right: 5vw;
			font-size: 2.5em;
			color: white;
		}

		.mediaIcon {
			margin: 0.3em;
			color: inherit;
		}

		.infoDiv {
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			text-align: center;
		}

		.imageWelcome {
			display: flex;
			justify-content: center;
			align-items: center;
			position: relative;
			background-size: cover;
			background-repeat: no-repeat;
			height: 100vh;
			/* box-sizing: border-box; */
		}

	</style>