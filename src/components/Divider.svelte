<script>
    export let anchorId;
</script>

<div class="divider" id={anchorId}>
    <div class="div-transparent" />
    <img src="../assets/monogram.png" alt="monogram">
</div>

<style>
    .divider {
		margin: 6rem 0;
		position: relative;
		height: 3.5rem;
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
			rgb(194, 132, 133),
			transparent,
			rgb(194, 132, 133),
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
