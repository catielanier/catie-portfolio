<script>
	const currentYear = new Date().getFullYear();
</script>

<div class="footer-container">
	<footer>
		<div class="copyright">
			© 2020-{currentYear} Catie Lanier, all rights reserved.
		</div>
		<div class="framework">
			Created using
			<a href="https://svelte.dev" target="_blank">
				<span>Svelte</span>
			</a>
		</div>
	</footer>
</div>

<style>
	.footer-container {
		padding-top: 40px;
		padding-bottom: 20px;
		background: #fdecef;
	}
	footer {
		margin: 0 auto;
		width: 100%;
		max-width: 1280px;
		background: #6b4e5c;
		font-family: "Work Sans", sans-serif;
		color: #fff9f5;
		font-size: 2rem;
		border-radius: 5px;
		padding: 5px 10px 11.5px;
		display: grid;
		grid-template-columns: 1fr 1fr;
	}

	.framework {
		text-align: right;
	}

	a {
		color: #fff9f5;
		text-decoration: underline;
	}

	a span {
		transition: all 0.3s ease-in-out;
	}

	a:hover span {
		color: #ead7a3;
	}
	@media (max-width: 1280px) {
		footer {
			width: 90%;
		}
	}

	@media (max-width: 424px) {
		footer {
			font-size: 1.8rem;
			padding-bottom: 10px;
			grid-template-rows: 1fr;
			grid-template-columns: 1fr;
		}
		.framework {
			text-align: left;
		}
	}
	@media (max-width: 320px) {
		footer {
			font-size: 1.6rem;
		}
	}
</style>
