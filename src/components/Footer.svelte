<script>
	const currentYear = new Date().getFullYear();
</script>

<footer class="footer">
	<div class="container">
		<div class="copyright">
			© 2020–{currentYear} Catie Lanier, all rights reserved.
		</div>
		<div class="framework">
			Created with
			<a href="https://svelte.dev" target="_blank" rel="noopener noreferrer">
				<span>Svelte</span>
			</a>
		</div>
	</div>
</footer>

<style>
	.footer {
		background: #fdecef;
		padding-block: 28px 20px;
	}

	.container {
		max-width: 1280px;
		margin: 0 auto;
		padding-inline: max(16px, env(safe-area-inset-left))
			max(16px, env(safe-area-inset-right));
		display: grid;
		grid-template-columns: 1fr 1fr;
		align-items: center;
		gap: 12px;
		background: #6b4e5c;
		color: #fff9f5;
		font-family: "Work Sans", sans-serif;
		font-size: clamp(1.5rem, 1.8vw, 2rem);
		border-radius: 8px;
		padding: 10px 16px;
	}

	.framework {
		text-align: right;
	}

	a {
		color: #fff9f5;
		text-decoration: underline;
		text-underline-offset: 3px;
		transition: color 0.3s ease;
	}

	a span {
		transition: color 0.3s ease-in-out;
	}

	a:hover span {
		color: #ead7a3;
	}

	@media (max-width: 640px) {
		.container {
			grid-template-columns: 1fr;
			text-align: center;
			font-size: 1.6rem;
		}
		.framework {
			text-align: center;
		}
	}
</style>
