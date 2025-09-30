<script>
	import notez from "../assets/notez.png";
	import elixir from "../assets/elixir.png";
	import jobHunt from "../assets/job-hunt.png";
	import whiffCityScoreboard from "../assets/whiff-city-scoreboard.png";
	import smrt from "../assets/smrt.png";

	const portfolioPieces = [
		{
			title: "Elixir Day Spa",
			tools: "Svelte / Firebase / CSS",
			description:
				"A website for a local day spa that I made to modernize the client's business website, built to her specifications. Svelte was used for fast builds and low bundle size. I included a carousel gallery to showcase her studio, and helped maintain her solid SEO rankings.",
			previewLink: "https://elixirdayspa.ca",
			githubRepo: "elixir-day-spa",
			file: elixir,
		},
		{
			title: "Whiff City Scoreboard",
			tools: "Svelte / TypeScript / Firebase / Websockets / CSS",
			description:
				"Developed a cross-platform web app for SMRT eSports that delivers a live-updating, stream-ready scoreboard overlay compatible with OBS and XSplit. Integrated Start.gg’s GraphQL API for match queue retrieval and score submission, with a debounced UI for real-time updates. Also built a stream queue to notify players onsite of upcoming streamed matches.",
			previewLink:
				"https://scoreboard.smrtesports.com/scoreboard/-ONME5VZUomKnVpSicbz",
			githubRepo: "whiff-city-firebase",
			file: whiffCityScoreboard,
		},
		{
			title: "SMRT eSports",
			tools: "Next.js / TypeScript / TailwindCSS / API / i18n",
			description:
				"A website I made using SSR in Next.js for an eSports organization. The site features i18n in Korean, Japanese, Mandarin, Spanish, and French, as well as a rotating gallery of event photos and a custom component for sanitizing anchor links from i18n dictionaries. Future plans include dynamic event pages and a blog.",
			previewLink: "https://smrtesports.com",
			githubRepo: "smrt-esports",
			file: smrt,
		},
		{
			title: "NoteZ",
			tools: "React / Material UI / Hooks / i18n / Node.js / Express / MongoDB",
			description:
				"This note app is designed for the storage and retrieval of notes meant for specific scenarios, such as matchups within competitive gaming. You are also able to further filter the notes based on specified data, so as to make them easier to read.",
			previewLink: "https://checkthenotez.com",
			githubRepo: "notez",
			file: notez,
		},
		{
			title: "Job Hunt",
			tools: "React / TypeScript / Hooks / CSS / Python / Flask / MongoDB",
			description:
				"This app allows you to track your job applications more easily. With this app, you can create, update and delete job applications and their statuses, as well as track the job posting and your contact within the company. It also shows you statistics on your job hunt.",
			previewLink: "https://job-hunt.catielanier.ca",
			githubRepo: "job-hunt",
			file: jobHunt,
		},
	];
</script>

<section class="portfolio">
	<div class="container">
		<h2>Portfolio</h2>

		{#each portfolioPieces as piece, i}
			<article class="project">
				<div class="media">
					<img
						src={piece.file}
						alt={piece.title}
						loading="lazy"
						decoding="async"
					/>
				</div>

				<div class="content">
					<h3>{piece.title}</h3>
					<p class="tools">{piece.tools}</p>
					<p>{piece.description}</p>
					<p class="links">
						<a
							href={piece.previewLink}
							target="_blank"
							rel="noopener noreferrer"
						>
							<span>View the project online.</span>
						</a>
					</p>
					<p class="links">
						<a
							href={`https://github.com/catielanier/${piece.githubRepo}`}
							target="_blank"
							rel="noopener noreferrer"
						>
							<span>View the source code.</span>
						</a>
					</p>
				</div>
			</article>
		{/each}

		<div class="cta">
			<a
				href="https://github.com/catielanier"
				target="_blank"
				class="button"
				rel="noopener noreferrer"
			>
				<span></span><span></span><span></span><span></span>
				See What I'm Working On
			</a>
		</div>
	</div>
</section>

<style>
	/* section background stays full-bleed */
	.portfolio {
		background: #fdecef;
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
		margin: 0 0 0.75rem 0;
		color: #3a2f2f;
	}

	/* project card layout */
	.project {
		display: grid;
		grid-template-columns: 1fr; /* mobile-first: stack */
		gap: clamp(16px, 3.5vw, 32px);
		align-items: center;
		margin-block: clamp(20px, 4vw, 40px);
	}

	/* image first on mobile */
	.media {
		order: 1;
	}
	.content {
		order: 2;
	}

	.media img {
		width: 100%;
		height: auto;
		display: block;
		border-radius: 8px;
		box-shadow: 0 8px 28px rgba(0, 0, 0, 0.08);
	}

	h3 {
		font-family: "Cormorant Garamond", serif;
		font-size: clamp(20px, 2.6vw, 32px);
		font-weight: 700;
		margin: 0;
		color: #6b4e5c;
	}
	.tools {
		margin: 0.25rem 0 0.5rem;
		font-size: clamp(13px, 1.6vw, 15px);
		color: #6b4e5c;
	}
	.links {
		font-family: "Work Sans", sans-serif;
		font-size: clamp(14px, 1.8vw, 18px);
		margin: 0.35rem 0;
	}
	.links a {
		text-decoration: underline;
		color: #f7a3b4;
	}
	.links a span {
		color: #6b4e5c;
		transition: color 0.2s ease;
	}
	.links a:hover span {
		color: #f7a3b4;
	}

	/* tablet/desktop: two columns; alternate sides automatically */
	@media (min-width: 900px) {
		.project {
			grid-template-columns: 1.1fr 0.9fr;
		}
		/* odd: image right, text left (default) */
		.project:nth-child(odd) .media {
			order: 2;
		}
		.project:nth-child(odd) .content {
			order: 1;
		}
		/* even: image left, text right */
		.project:nth-child(even) .media {
			order: 1;
		}
		.project:nth-child(even) .content {
			order: 2;
		}

		.media img {
			border-radius: 10px;
		}
	}

	/* CTA button (kept from your styles) */
	.cta {
		margin-top: clamp(16px, 4vw, 28px);
	}
	a.button {
		cursor: pointer;
		position: relative;
		padding: 15px 20px;
		background: #fdecef;
		font-family: "Work Sans", sans-serif;
		text-transform: uppercase;
		font-size: 1.7rem;
		border-radius: 10px;
		border: 0;
		transition: all 1s;
		color: #3a2f2f;
		text-decoration: none;
		display: inline-block;
	}
	a.button:after,
	a.button:before {
		content: "";
		width: 10px;
		height: 10px;
		position: absolute;
		transition: all 1s;
	}
	a.button:after {
		top: -1px;
		left: -1px;
		border-top: 2px solid #e5a4b3;
		border-left: 2px solid #e5a4b3;
		border-top-left-radius: 10px;
	}
	a.button:before {
		bottom: -1px;
		right: -1px;
		border-bottom: 2px solid #e5a4b3;
		border-right: 2px solid #e5a4b3;
		border-bottom-right-radius: 10px;
	}
	a.button:hover {
		border-top-right-radius: 10px;
		border-bottom-left-radius: 10px;
		color: #e5a4b3;
	}
	a.button:hover:before {
		border-bottom-color: #ead7a3;
		border-right-color: #ead7a3;
	}
	a.button:hover:after {
		border-top-color: #ead7a3;
		border-left-color: #ead7a3;
	}
</style>
