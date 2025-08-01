<script>
	const portfolioPieces = [
		{
			title: "NoteZ",
			tools: "React / Material UI / Hooks / i18n / Node.js / Express / MongoDB",
			description:
				"This note app is designed for the storage and retrieval of notes meant for specific scenarios, such as matchups within competitive gaming. You are also able to further filter the notes based on specified data, so as to make them easier to read.",
			previewLink: "https://checkthenotez.com",
			githubRepo: "notez",
			imageName: "notez",
		},
		{
			title: "Elixir Day Spa",
			tools: "Svelte / Firebase / CSS",
			description:
				"A website for a local day spa that I made to modernize the client's business website, built to her specifications. Svelte was used for fast builds and low bundle size. I included a carousel gallery to showcase her studio, and helped maintain her solid SEO rankings.",
			previewLink: "https://elixirdayspa.ca",
			githubRepo: "elixir-day-spa",
			imageName: "elixir",
		},
		{
			title: "Job Hunt",
			tools: "React / TypeScript / Hooks / CSS / Python / Flask / MongoDB",
			description:
				"This app allows you to track your job applications more easily. With this app, you can create, update and delete job applications and their statuses, as well as track the job posting and your contact within the company. It also shows you statistics on your job hunt.",
			previewLink: "https://job-hunt.catielanier.ca",
			githubRepo: "job-hunt",
			imageName: "job-hunt",
		},
		{
			title: "Whiff City Scoreboard",
			tools: "Svelte / TypeScript / Firebase / Websockets / CSS",
			description:
				"Developed a cross-platform web app for SMRT eSports that delivers a live-updating, stream-ready scoreboard overlay compatible with OBS and XSplit. Integrated Start.gg’s GraphQL API for match queue retrieval and score submission, with a debounced UI for real-time updates. Also built a stream queue to notify players onsite of upcoming streamed matches.",
			previewLink:
				"https://scoreboard.smrtesports.com/scoreboard/-ONME5VZUomKnVpSicbz",
			githubRepo: "whiff-city-firebase",
			imageName: "whiff-city-scoreboard",
		},
		{
			title: "SMRT eSports",
			tools: "Next.js / TypeScript / TailwindCSS / API / i18n",
			description:
				"A website I made using SSR in Next.js for an eSports organization. The site features i18n in Korean, Japanese, Mandarin, Spanish, and French, as well as a rotating gallery of event photos and a custom component for sanitizing anchor links from i18n dictionaries. Future plans include dynamic event pages and a blog.",
			previewLink: "https://smrtesports.com",
			githubRepo: "smrt-esports",
			imageName: "smrt",
		},
		// {
		// 	title: "Vue Blog",
		// 	tools: "Nuxt / Vuex / CSS / Node.js / Express / MongoDB",
		// 	description:
		// 		"A Vue full stack app that I built to create a simple content management system and frontend for a blog. It allows for new user creation, user admin to create multiple authors, posting and commenting.",
		// 	previewLink: "https://blog.catielanier.ca",
		// 	githubRepo: "vue-blog",
		// 	imageName: "blog",
		// },
	];
</script>

<section>
	<h2>Portfolio</h2>
	{#each portfolioPieces as piece, index}
		<div class="grid-container" key={index}>
			<div>
				<h3>{piece.title}</h3>
				<p class="tools">{piece.tools}</p>
				<p>{piece.description}</p>
				<div class="link">
					<a href={piece.previewLink} target="_blank">
						<span>View the project online.</span>
					</a>
				</div>
				<div class="link">
					<a
						href={`https://github.com/catielanier/${piece.githubRepo}`}
						target="_blank"
					>
						<span>View the source code.</span>
					</a>
				</div>
			</div>
			<div><img src={`assets/${piece.imageName}.png`} alt={piece.title} /></div>
		</div>
	{/each}
	<div>
		<a href="https://github.com/catielanier" target="_blank" class="button">
			<span />
			<span />
			<span />
			<span />
			See What I'm Currently Working On
		</a>
	</div>
</section>

<style>
	h3 {
		font-family: "Comfortaa", sans-serif;
		font-size: 3.2rem;
		font-weight: 700;
		margin-bottom: 0;
	}
	.grid-container {
		margin: 20px auto;
		display: grid;
		grid-template-columns: 1.5fr 1fr;
		grid-gap: 35px;
		align-items: center;
	}
	p.tools {
		margin-top: 0;
		font-size: 1.5rem;
		color: #c28485;
	}
	.link {
		font-family: "Arvo", serif;
		font-size: 2rem;
		margin-bottom: 25px;
	}
	.link a {
		text-decoration: underline;
		color: #f7a3b4;
	}
	span {
		color: #303030;
		transition: all 0.3s ease-in-out;
	}

	.link a:hover span {
		color: #f7a3b4;
	}

	.grid-container img {
		width: 100%;
	}

	a.button {
		cursor: pointer;
		margin-top: 15px;
		position: relative;
		padding: 15px 20px;
		background: #fcccd3;
		font-family: "Comfortaa", serif;
		text-transform: uppercase;
		font-size: 1.6rem;
		border-top-right-radius: 10px;
		border-bottom-left-radius: 10px;
		border: 0;
		transition: all 1s;
		color: #c28485;
	}
	a.button:after,
	a.button:before {
		content: " ";
		width: 10px;
		height: 10px;
		position: absolute;
		transition: all 1s;
	}
	a.button:after {
		top: -1px;
		left: -1px;
		border-top: 2px solid #c28485;
		border-left: 2px solid #c28485;
	}
	a.button:before {
		bottom: -1px;
		right: -1px;
		border-bottom: 2px solid #c28485;
		border-right: 2px solid #c28485;
	}
	a.button:hover {
		border-top-right-radius: 0px;
		border-bottom-left-radius: 0px;
		text-decoration: none;
	}
	a.button:hover:before,
	a.button:hover:after {
		width: 100%;
		height: 100%;
	}
	@media (max-width: 768px) {
		.grid-container {
			align-items: initial;
			grid-template-columns: 1.2fr 1fr;
		}
	}

	@media (max-width: 424px) {
		.grid-container {
			grid-template-columns: 1fr;
			grid-template-rows: 1fr 2fr;
		}

		.grid-container > div:first-of-type {
			grid-row: 2;
		}
	}

	@media (max-width: 320px) {
		.grid-container {
			grid-template-rows: 0.5fr 1.5fr;
		}
	}
</style>
