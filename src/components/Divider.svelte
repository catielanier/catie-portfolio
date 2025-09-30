<script>
	export let anchorId;
	export let isInverse = false;
	import monogram from "../assets/monogram.png";
</script>

<section class={isInverse ? "inverse" : ""}>
	<div class="container">
		<div class="divider" id={anchorId}>
			<div class="div-transparent" />
			<img src={monogram} alt="monogram" />
		</div>
	</div>
</section>

<style>
	section {
		background-image: linear-gradient(
			to bottom,
			rgb(253, 236, 239),
			rgb(255, 249, 245)
		);
	}

	section.inverse {
		background-image: linear-gradient(
			to bottom,
			rgb(255, 249, 245),
			rgb(253, 236, 239)
		);
	}
	.divider {
		padding: 6rem 0;
		position: relative;
		height: 3.5rem;
	}

	.container {
		max-width: 1280px;
		margin: 0 auto;
	}

	.div-transparent {
		content: " ";
		position: absolute;
		top: 50%;
		left: 0;
		right: 0;
		transform: translateY(-50%);
		width: 100%;
		height: 2px;
		background-image: linear-gradient(
			to right,
			transparent,
			rgb(229, 164, 179),
			transparent,
			rgb(229, 164, 179),
			transparent
		);
	}
	.divider img {
		margin: 6rem 0;
		height: 3.5rem;
		position: absolute;
		top: 0;
		left: 50%;
		transform: translateX(-50%);
	}
</style>
