<script>
	import catie from "../assets/catie.jpg";
	const languageGreetings = [
		{ text: "Hello all", lang: "en" },
		{ text: "여러분 안녕하세요", lang: "ko" },
		{ text: "大家好", lang: "zh" },
		{ text: "皆さんこんにちは", lang: "ja" },
		{ text: "Bonjour à tous", lang: "fr" },
		{ text: "Saluton al ĉiuj", lang: "eo" },
		{ text: "Halo a h-uile duine", lang: "gd" },
	];
</script>

<header id="home">
	<div class="container">
		<div>
			<h1>Software Engineer · Creative Developer</h1>

			<!-- ✅ replace your long bio with this single value line -->
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
				<a href="#portfolio">View my work</a>
				<span aria-hidden="true">·</span>
				<a href="#contact">Work with me</a>
			</p>
		</div>

		<div>
			<div class="header-image">
				<img src={catie} alt="Catie Lanier" />
			</div>
		</div>
	</div>
</header>

<style>
	/* keep your font family + sizes, but remove the fixed height */
	h1 {
		font-family: "Comfortaa", sans-serif;
		font-size: 3.8rem;
		line-height: 1.8;
		/* height: 7.2rem;  ⟵ remove this to stop clipping/awkward spacing */
		margin: 0 0 0.25rem;
	}

	header {
		background: #fdecef;
	}

	.container {
		max-width: 1280px;
		margin: 0 auto;
		padding-top: 120px;
		display: grid;
		grid-template-columns: 2fr 1fr;
		grid-gap: 30px;
		align-items: center;
	}

	h2.tagline {
		font-size: 2.5rem;
		line-height: 2.5rem;
	}

	.hero-links {
		font-family: "Arvo", serif; /* matches your portfolio link text */
		font-size: 2rem;
		margin-top: 1rem;
	}

	.hero-links a {
		text-decoration: underline;
		color: #c28485; /* your rose accent — darker, readable */
		transition: color 0.2s ease-in-out;
	}

	.hero-links a:hover {
		color: #f7a3b4; /* lighter pink on hover */
	}

	.hero-links span {
		color: #303030; /* neutral dot */
		opacity: 0.6;
	}

	img {
		width: 100%;
		border-radius: 50%;
	}
	.header-image {
		border-radius: 45%;
	}

	/* your existing responsive rules, with height removed */
	@media (max-width: 1024px) {
		h1 {
			font-size: 5.7rem;
		}
	}

	@media (max-width: 768px) {
		header {
			grid-template-columns: 1.5fr 1fr;
			align-items: initial;
		}
		h1 {
			font-size: 3.5rem;
		}
	}

	@media (max-width: 424px) {
		h1 {
			font-size: 2.9rem;
		}
		header {
			padding-top: 50px;
			grid-template-rows: 1fr 2fr;
			grid-template-columns: 100%;
			grid-auto-flow: dense;
			margin: 0 auto;
			grid-gap: 0;
		}
		header div:first-of-type {
			grid-row: 2;
		}
		header div:last-child {
			text-align: center;
		}
		img {
			transform: none;
		}
	}

	@media (max-width: 375px) {
		h1 {
			font-size: 2.8rem;
		}
	}
	@media (max-width: 320px) {
		h1 {
			font-size: 2.3rem;
		}
		header {
			grid-template-rows: 0.5fr 2fr;
		}
	}
</style>
