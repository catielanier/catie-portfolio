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
			title: "Job Hunt",
			tools: "React / TypeScript / Hooks / CSS / Python / Flask / MongoDB",
			description:
				"This app allows you to track your job applications more easily. With this app, you can create, update and delete job applications and their statuses, as well as track the job posting and your contact within the company. It also shows you statistics on your job hunt.",
			previewLink: "https://job-hunt.catielanier.ca",
			githubRepo: "job-hunt",
			imageName: "job-hunt",
		},

		{
			title: "Vue Blog",
			tools: "Nuxt / Vuex / CSS / Node.js / Express / MongoDB",
			description:
				"A Vue full stack app that I built to create a simple content management system and frontend for a blog. It allows for new user creation, user admin to create multiple authors, posting and commenting.",
			previewLink: "https://blog.catielanier.ca",
			githubRepo: "vue-blog",
			imageName: "blog",
		},
		{
			title: "Date Changer",
			tools: "Vue / API / Node.js / Express / MongoDB",
			description:
				"A web app I created for iCademy Middle East that utilizes the Canvas LMS API to allow teachers to automate the process of setting assignment dates. The app runs an algorithm to check the duration of the course, the number assignments, and automatically changes the due dates at a fixed interval.",
			previewLink: "https://icad-dubai-dates.now.sh",
			githubRepo: "date-changer",
			imageName: "date-changer",
		},
		{
			title: "Name Changer",
			tools: "React / API / Node.js / Express / Firebase",
			description:
				"A web app I created for iCademy Middle East that utilizes the Canvas LMS API to allow teachers to rename their course items in bulk by automating the renaming process. It features a Node.js proxy server to handle updating the data on the Canvas API, and a Firebase to track and undo changes.",
			previewLink: "https://icad-name-changer.now.sh",
			githubRepo: "name-changer",
			imageName: "name-changer",
		},
		{
			title: "Maxshop",
			tools: "HTML / Sass / jQuery",
			description:
				"A simple PSD wireframe conversion I made during bootcamp. This shows off great usage of Flexbox and CSS Grid which helps to maintain viewability on responsive design.",
			previewLink: "https://maxshop.catielanier.ca",
			githubRepo: "corey_lanier_project2",
			imageName: "maxshop",
		},
	];
</script>

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
						target="_blank">
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
