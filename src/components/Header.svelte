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
	<div>
		<h1>
			<div id="typed-strings">
				{#each languageGreetings as greeting}
					<p class={`greeting-${greeting.lang}`}>{greeting.text}!</p>
				{/each}
			</div>
			<span id="typed" />
		</h1>

		<!-- ✅ replace your long bio with this single value line -->
		<p class="tagline">
			Freelance Software Engineer helping startups, esports orgs, and small
			businesses build fast, clean apps — serving the Greater Toronto Area and
			Simcoe County.
		</p>

		<p>
			My name is Catie Lanier, and I am a multilingual (English, Mandarin,
			Korean, Japanese, Esperanto) full stack developer based in Toronto. I am a
			graduate of Juno College's Web Development Immersive, and am completely
			fluent in Front End and Full Stack development.
		</p>

		<p>
			I have a deep passion for writing clean JavaScript, and React and Vue.js
			are two of my favourite frameworks to work in. I also enjoy learning and
			teaching new technologies and frameworks that help make designs more
			effective and user friendly.
		</p>

		<p>
			Before starting my career in tech, I lived in China and South Korea for 5
			years teaching English as a Second Language, and am leveraging my
			interpersonal and communication skills to develop clean code. Alongside
			knowledge and skills, I bring curiosity, enthusiasm, and a whole lot of
			care to everything I do.
		</p>

		<p>
			Outside of coding, I enjoy playing video games, playing bass guitar,
			ballet, fashion, and spending time with my cats.
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
</header>

<style>
	/* keep your font family + sizes, but remove the fixed height */
	h1 {
		font-family: "Comfortaa", sans-serif;
		font-size: 7.1rem;
		line-height: 1.05;
		/* height: 7.2rem;  ⟵ remove this to stop clipping/awkward spacing */
		margin: 0 0 0.25rem;
	}

	header {
		padding-top: 120px;
		display: grid;
		grid-template-columns: 2fr 1fr;
		grid-gap: 30px;
		align-items: center;
	}

	/* subtle, on-brand supporting line */
	.tagline {
		font-family: "Comfortaa", sans-serif;
		font-weight: bold;
		margin: 2rem 0 0.6rem;
		max-width: 62ch;
		opacity: 0.9;
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
