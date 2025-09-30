<script>
	import { onMount } from "svelte";
	import Carousel from "svelte-carousel/src/components/Carousel/Carousel.svelte";

	let carousel;
	let autoplayEnabled = true;
	let isMobile = false;

	onMount(() => {
		if (typeof window !== "undefined") {
			const reduced = window.matchMedia("(prefers-reduced-motion: reduce)");
			autoplayEnabled = !reduced.matches;

			const resize = () => {
				isMobile = window.innerWidth < 768; // stack on <768px
			};
			resize();
			window.addEventListener("resize", resize);
		}
	});

	const testimonials = [
		{
			name: "Ragan MacDonald",
			company: "iCademy Middle East",
			text: "We hired Catie to build automation apps for setting assignment dates for our LMS. She was communicative, efficient, and delivered a great product. I would highly recommend her for any web development needs.",
		},
		{
			name: "Jennifer Lee",
			company: "SMRT eSports",
			text: "Catie was very attentive to the needs of SMRT eSports when she developed our website and scoreboard. She suggested coding languages and design for the website that considered growth in our needs and functionalities. As an eSports organization, we also stream tournaments and matches. Catie designed and developed a team tournament scoreboard which increased audience retention and added to the professionalism of SMRT eSports. We were in good hands every step of the way.",
		},
		{
			name: "Jeffrey Xu",
			company: "Allied Technical Solutions",
			text: "Catie, an alumni of HackerYou College of Technology, was paired up with me as my bootcamp buddy during my time as a student of their Web Development Immersive program. She has shown fantastic support and shared valuable knowledge as well as experience in great modesty.",
		},
	];
</script>

<section class="testimonials">
	<div class="container">
		<h2>Testimonials</h2>
		<p class="lede">What people say about me:</p>

		{#if isMobile}
			<!-- Mobile/tablet: stacked -->
			{#each testimonials as t}
				<article class="testimonial">
					<blockquote>
						<p class="quote">{t.text}</p>
						<footer class="byline">— {t.name}, {t.company}</footer>
					</blockquote>
				</article>
			{/each}
		{:else}
			<!-- Desktop: carousel -->
			<Carousel
				bind:this={carousel}
				autoplay={autoplayEnabled}
				pauseOnHover
				pauseOnFocus
				loop
				autoplayDuration={8000}
				itemsToShow={1}
				itemsToScroll={1}
				aria-label="Client testimonials carousel"
			>
				{#each testimonials as t}
					<div class="slide">
						<blockquote>
							<p class="quote">{t.text}</p>
							<footer class="byline">— {t.name}, {t.company}</footer>
						</blockquote>
					</div>
				{/each}
			</Carousel>
		{/if}
	</div>
</section>

<style>
	.testimonials {
		background: #fff9f5;
		padding-block: clamp(28px, 6vw, 72px);
	}
	.container {
		max-width: 1280px;
		margin: 0 auto;
		padding-inline: clamp(16px, 4vw, 40px);
	}

	h2 {
		font-family: "Cormorant Garamond", serif;
		font-size: clamp(22px, 3.2vw, 32px);
		font-weight: 600;
		margin: 0 0 0.5rem;
		color: #3a2f2f;
	}
	.lede {
		font-size: clamp(14px, 1.8vw, 18px);
		margin: 0 0 1.25rem;
		color: #3a2f2f;
	}

	/* shared blockquote style */
	blockquote {
		margin: 0;
		padding: clamp(16px, 3vw, 24px);
		background: #fff;
		border-radius: 12px;
		border: 1px solid #c9c6d9;
		box-shadow: 0 6px 16px rgba(0, 0, 0, 0.05);
	}
	.quote {
		margin: 0;
		font-size: clamp(16px, 2vw, 20px);
		line-height: 1.6;
		color: #3a2f2f;
	}
	.byline {
		margin-top: 0.75rem;
		text-align: right;
		font-family: "Cormorant Garamond", serif;
		font-style: italic;
		font-size: clamp(14px, 1.8vw, 18px);
		color: #6b4e5c;
	}

	/* --- Carousel desktop fixes --- */
	:global(.carousel),
	:global(.carousel .viewport),
	:global(.carousel .track),
	:global(.carousel .slide) {
		height: auto !important;
	}
	:global(.carousel .viewport) {
		overflow: visible !important;
	}
	:global(.carousel .slide) {
		white-space: normal !important;
	}
	:global(.carousel .indicators button) {
		background: #e9dbe2;
	}
	:global(.carousel .indicators button.active) {
		background: #e5a4b3;
		box-shadow: 0 0 0 2px #ead7a3 inset;
	}
</style>
