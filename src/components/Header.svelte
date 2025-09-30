<script>
	export let isKr = false;
	import catie from "../assets/catie.jpg";
</script>

<header id="home">
	<div class="container">
		<div class="hero-media">
			<div class="header-image">
				<img src={catie} alt="Portrait of Catie Lanier" />
			</div>
		</div>

		<div class="hero-copy">
			<h1>Software Engineer · Creative Developer</h1>

			<h2 class="tagline">
				Building fast, clean apps with a touch of elegance — serving the Greater
				Toronto Area and beyond.
			</h2>

			<p>
				I’m Catie Lanier, a multilingual full stack developer in English,
				Mandarin, and Korean. My work bridges technical precision with
				creativity, helping startups, esports organizations, and small
				businesses launch digital experiences that feel as polished as they are
				powerful.
			</p>

			<p>
				With a background in both software engineering and the performing arts,
				I bring curiosity, design sense, and a collaborative spirit to every
				project. Whether it’s React, Vue, or full stack systems, my focus is on
				delivering code that’s clean, maintainable, and delightful to use.
			</p>

			<p class="hero-links">
				{#if !isKr}
					<a href="/resume.pdf" target="_blank" rel="noopener noreferrer"
						><span>View my resume</span></a
					>
					<span aria-hidden="true">·</span>
				{/if}
				<a href="#portfolio"><span>View my work</span></a>
				<span aria-hidden="true">·</span>
				<a href="#contact"><span>Work with me</span></a>
			</p>
		</div>
	</div>
</header>

<style>
	:root {
		--bg-blush: #fdecef;
		--text: #3a2f2f;
		--mauve: #6b4e5c;
		--pink: #e5a4b3;
		--gold: #ead7a3;
		--container-w: 1280px;
		--space-section: clamp(32px, 6vw, 88px);
		--gap: clamp(16px, 3.5vw, 32px);
	}

	header {
		background: var(--bg-blush);
		padding-block: var(--space-section);
	}
	.container {
		max-width: var(--container-w);
		margin: 0 auto;
		padding-inline: clamp(16px, 4vw, 40px);
		display: grid;
		grid-template-columns: 1fr;
		gap: var(--gap);
		align-items: center;
	}

	/* image sits on top by default (mobile-first) */
	.hero-media {
		order: 1;
		text-align: center;
	}
	.hero-copy {
		order: 2;
	}

	h1 {
		font-family: "Cormorant Garamond", serif;
		font-size: clamp(28px, 5vw, 44px);
		line-height: 1.25;
		font-weight: 700;
		margin: 0 0 0.5rem 0;
		color: var(--text);
	}
	.tagline {
		font-family: "Work Sans", sans-serif;
		font-size: clamp(16px, 2.4vw, 20px);
		line-height: 1.45;
		color: var(--mauve);
		font-weight: 600;
		margin: 0 0 0.9rem 0;
	}
	p {
		font-family: "Work Sans", sans-serif;
		font-size: clamp(16px, 1.25vw, 18px);
		line-height: 1.65;
		color: var(--text);
		margin: 0.65rem 0;
		max-width: 68ch;
	}

	.hero-links {
		display: flex;
		flex-wrap: wrap;
		gap: 10px 18px;
		align-items: center;
		margin-top: 0.75rem;
		font-size: clamp(14px, 1.6vw, 18px);
	}
	.hero-links a {
		text-decoration: none;
		position: relative;
		color: var(--pink);
	}
	.hero-links a span {
		color: var(--mauve);
		transition: color 0.2s ease;
	}
	.hero-links a:hover span {
		color: var(--pink);
	}
	.hero-links span[aria-hidden] {
		opacity: 0.6;
	}

	.header-image {
		max-width: min(420px, 85vw);
		margin-inline: auto;
	}
	.header-image img {
		width: 100%;
		height: auto;
		border-radius: 50%;
		box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
	}

	/* tablet+ two-column layout: put text left, image right */
	@media (min-width: 900px) {
		.container {
			grid-template-columns: 1.4fr 1fr;
			align-items: center;
		}
		.hero-media {
			order: 2;
			text-align: right;
		}
		.hero-copy {
			order: 1;
		}
	}
</style>
