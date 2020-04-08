<script>
import Nested from './Nested.svelte';

	export let name;
	name = '<h2>Valera</h2>';
	let src = '/images/entrance/000040.JPG';

	const handleHello = (event) => {
    alert(`That is from another component: ${event.detail.text}`);
	};

</script>

<!-- <main style="background-image: url('images/entrance/000040.JPG')"> -->
  <div class="imageWelcome" style="background-image: url('images/entrance/000040.JPG')">
  <p>HELLO</p>
  <button>
	Click me
  </button>
  </div>
<!-- </main> -->

<style>

body {
    margin: 0;
    text-align: center;
}

	main {
		text-align: center;
		/* padding: 1em;
		max-width: 240px;
		margin: 0 auto; */
	}

	p {
		color: white;
		font-size: 2em;
		align-self: 'center';
	}

  .imageWelcome {
    background-size: cover;
    background-repeat: repeat;
    height: 95vh;
    box-sizing: border-box;
  }

	img {
		height: 500px;
		width: 500px;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>