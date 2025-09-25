<script>
	export let anchorId;
	export let isInverse = false;
	import monogram from "../assets/monogram.png";
</script>

<div class="divider {isInverse && 'inverse'}" id={anchorId}>
	<div class="div-transparent" />
	<img src={monogram} alt="monogram" />
</div>

<style>
	.divider {
		margin: 6rem 0;
		position: relative;
		height: 3.5rem;
		background-image: linear-gradient(
			to bottom,
			rgb(253, 236, 239),
			rgb(255, 249, 245)
		);
	}

	.divider.inverse {
		background-image: linear-gradient(
			to bottom,
			rgb(255, 249, 245),
			rgb(253, 236, 239)
		);
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
		height: 3.5rem;
		position: absolute;
		top: 0;
		left: 50%;
		transform: translateX(-50%);
	}
</style>
