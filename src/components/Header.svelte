<script>
	const languageGreetings = [
		{
			text: "Hello all",
			lang: "en",
		},
		{
			text: "여러분 안녕하세요",
			lang: "ko",
		},
		{
			text: "大家好",
			lang: "zh",
		},
		{
			text: "皆さんこんにちは",
			lang: "ja",
		},
		{
			text: "Bonjour à tous",
			lang: "fr",
		},
		{
			text: "Saluton al ĉiuj",
			lang: "eo",
		},
		{
			text: "Halo a h-uile duine",
			lang: "gd",
		},
	];
</script>

<header id="home">
	<div>
		<h1>
			<div id="typed-strings">
				{#each languageGreetings as greeting}
					<p class={`greeting-${greeting.lang}`} key={greeting.lang}>
						{greeting.text}!
					</p>
				{/each}
			</div>
			<span id="typed" />
		</h1>
		<p>
			My name is Catie Lanier, and I am a multilingual (English, Mandarin,
			Korean, Japanese, Esperanto) full stack developer based in Toronto. I am a
			graduate of Juno College's Web Development Immersive, and am completely
			fluent in Front End and Full Stack development.
		</p>
		<p>
			I have a deep passion for writing clean Javascript, and React and Vue.js
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
			shopping and fashion, and spending time with my cats.
		</p>
	</div>
	<div>
		<div class="header-image">
			<img src="../assets/catie.jpg" alt="Catie Lanier" />
		</div>
	</div>
</header>

<style>
	h1 {
		font-family: "Comfortaa", sans-serif;
		font-size: 7.1rem;
		height: 7.2rem;
	}

	header {
		padding-top: 120px;
		display: grid;
		grid-template-columns: 2fr 1fr;
		grid-gap: 30px;
		align-items: center;
	}
	img {
		width: 100%;
		border-radius: 50%;
	}
	.header-image {
		border-radius: 45%;
	}

	@media (max-width: 1024px) {
		h1 {
			font-size: 5.7rem;
			height: 5.8rem;
		}
	}

	@media (max-width: 768px) {
		header {
			grid-template-columns: 1.5fr 1fr;
			align-items: initial;
		}
		h1 {
			font-size: 3.5rem;
			height: 3.6rem;
		}
	}

	@media (max-width: 424px) {
		h1 {
			font-size: 2.9rem;
			height: 3rem;
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
			height: 2.9rem;
		}
	}

	@media (max-width: 320px) {
		h1 {
			font-size: 2.3rem;
			height: 2.4rem;
		}
		header {
			grid-template-rows: 0.5fr 2fr;
		}
	}
</style>
