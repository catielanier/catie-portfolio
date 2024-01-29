<script>
    export let anchorId;
</script>

<div class="divider div-transparent" id={anchorId}>

</div>

<style>
    .divider {
		margin: 6rem 0;
		position: relative;
		height: 2px;
	}

	.div-transparent:before {
		content: "";
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		width: 100%;
		height: 2px;
		background-image: linear-gradient(
			to right,
			transparent,
			rgb(194, 132, 133),
			transparent
		);
	}

</style>
