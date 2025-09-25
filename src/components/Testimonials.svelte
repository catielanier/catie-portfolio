<script>
	import Carousel from "svelte-carousel/src/components/Carousel/Carousel.svelte";

	let carousel;

	const testimonials = [
		{
			name: "Ragan MacDonald",
			company: "iCademy Middle East",
			text: "We hired Catie to build automation apps for setting assignment dates for our LMS. She was communicative, efficient, and delivered a great product. I would highly recommend her for any web development needs.",
		},
		{
			name: "Jennifer Lee",
			company: "SMRT eSports",
			text: "Catie was very attentive to the needs of SMRT eSports when she developed our website and scoreboard.  She suggested coding languages and design for the website that considered growth in our needs and functionalities.  As an eSports organization, we also stream tournaments and matches.  Catie designed and developed a team tournament scoreboard which increased audience retention and added to the professionalism of SMRT eSports. We were in good hands every step of the way.",
		},
		{
			name: "Jeffrey Xu",
			company: "Allied Technical Solutions",
			text: "Catie, an alumni of HackerYou College of Technology, was paired up with me as my bootcamp buddy during my time as a student of their Web Development Immersive program. She has shown fantastic support and shared valuable knowledge as well as experience in great modesty.",
		},
	];
</script>

<section>
	<h2>Testimonials</h2>
	<p>What people say about me:</p>
	<div class="carousel-wrapper">
		<Carousel
			bind:this={carousel}
			autoplay
			pauseOnFocus
			autoplayDuration={8000}
		>
			{#each testimonials as testimonial}
				<div class="testimonial-slide">
					<blockquote>
						<p>{testimonial.text}</p>
						<footer>
							— {testimonial.name}, {testimonial.company}
						</footer>
					</blockquote>
				</div>
			{/each}
		</Carousel>
	</div>
</section>

<style>
	section {
		background: #fff9f5;
	}
	.carousel-wrapper footer {
		text-align: right;
		font-style: italic;
		margin-top: 1rem;
		font-family: "Neuton", serif;
		font-size: 1.7rem;
	}
</style>
