<script>
	const photo1 = 'images/gallery/photo1.jpeg';
	const photo2 = 'images/gallery/photo2.jpeg';
	const photo3 = 'images/gallery/photo3.jpeg';
	const photo4 = 'images/gallery/photo4.jpeg';
	const photo5 = 'images/gallery/photo5.jpeg';

	const images = [photo1, photo2, photo3, photo4, photo5];

</script>

<div class="parentDiv">
	<div class="galleryContainer">
		{#each images as image}
			<img class="galleryPic" src={image} alt="Film photos"/>
		{/each}
	</div>
</div>

<style>

.parentDiv {
	background-color: #383636;
	height: "100%";
}

.galleryPic {
	width: 60%;
	padding: 3em;
}

.galleryContainer {
	display: flex;
	flex-direction: column;
	align-items: center
}

</style>