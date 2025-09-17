<script>
	import javascript from "../assets/javascript.svg";
	import typescript from "../assets/typescript.svg";
	import react from "../assets/react.svg";
	import vue from "../assets/vue.svg";
	import svelte from "../assets/svelte.svg";
	import tailwind from "../assets/tailwind.svg";
	import sass from "../assets/sass.svg";
	import html from "../assets/html.svg";
	import css from "../assets/css.svg";
	import node from "../assets/node.svg";
	import express from "../assets/express.svg";
	import php from "../assets/php.svg";
	import laravel from "../assets/laravel.svg";
	import python from "../assets/python.svg";
	import flask from "../assets/flask.svg";
	import ruby from "../assets/ruby.svg";
	import rails from "../assets/rails.svg";
	import csharp from "../assets/csharp.svg";
	import dotnet from "../assets/dotnet.svg";
	import mongo from "../assets/mongo.svg";
	import postgresql from "../assets/postgresql.svg";
	import firebase from "../assets/firebase.svg";
	import supabase from "../assets/supabase.svg";
	import rust from "../assets/rust.svg";
	import kotlin from "../assets/kotlin.svg";
	import git from "../assets/git.svg";
	import vscode from "../assets/vscode.svg";
	import neovim from "../assets/neovim.svg";
	import graphql from "../assets/graphql.svg";
	import websockets from "../assets/websockets.svg";
	import docker from "../assets/docker.svg";
	import shell from "../assets/shell.svg";
	const skills = [
		// Frontend
		{ name: "JavaScript", type: "Frontend", file: javascript },
		{ name: "TypeScript", type: "Frontend", file: typescript },
		{ name: "React", type: "Frontend", file: react },
		{ name: "Vue", type: "Frontend", file: vue },
		{ name: "Svelte", type: "Frontend", file: svelte },
		{ name: "Tailwind CSS", type: "Frontend", file: tailwind },
		{ name: "Sass", type: "Frontend", file: sass },
		{ name: "HTML5", type: "Frontend", file: html },
		{ name: "CSS3", type: "Frontend", file: css },

		// Backend
		{ name: "Node.js", type: "Backend", file: node },
		{ name: "Express", type: "Backend", file: express },
		{ name: "PHP", type: "Backend", file: php },
		{ name: "Laravel", type: "Backend", file: laravel },
		{ name: "Python", type: "Backend", file: python },
		{ name: "Flask", type: "Backend", file: flask },
		{ name: "Ruby", type: "Backend", file: ruby },
		{ name: "Rails", type: "Backend", file: rails },
		{ name: "C#", type: "Backend", file: csharp },
		{ name: ".NET", type: "Backend", file: dotnet },
		{ name: "MongoDB", type: "Backend", file: mongo },
		{ name: "PostgreSQL", type: "Backend", file: postgresql },
		{ name: "Firebase", type: "Backend", file: firebase },
		{ name: "Supabase", type: "Backend", file: supabase },
		{ name: "Rust", type: "Backend", file: rust },
		{ name: "Kotlin", type: "Backend", file: kotlin },

		// Tooling
		{ name: "Git", type: "Tooling", file: git },
		{ name: "VSCode", type: "Tooling", file: vscode },
		{ name: "Neovim", type: "Tooling", file: neovim },
		{ name: "GraphQL", type: "Tooling", file: graphql },
		{ name: "WebSockets", type: "Tooling", file: websockets },
		{ name: "Docker", type: "Tooling", file: docker },
		{ name: "Shell Scripting", type: "Tooling", file: shell },
	];

	const categories = ["Frontend", "Backend", "Tooling"];
</script>

<section>
	<h2>Skills</h2>

	{#each categories as category}
		<div class="category">
			<h3>{category}</h3>
			<div class="skills-grid">
				{#each skills.filter((s) => s.type === category) as skill}
					<div class="skill">
						<img src={skill.file} alt={skill.name} />
						<p>{skill.name}</p>
					</div>
				{/each}
			</div>
		</div>
	{/each}
</section>

<style>
	section {
		padding: 2rem 1rem;
	}

	.category {
		margin-bottom: 2.5rem;
	}
	.category h3 {
		font-family: "Comfortaa", sans-serif;
		font-size: 2.1rem;
		margin-bottom: 1rem;
		/* removed uppercase transform */
		letter-spacing: 0.05em;
		color: #333;
	}

	.skills-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
		gap: 1.5rem;
	}

	.skill {
		text-align: center;
		padding: 1rem;
		border: 1px solid #fcccd3;
		border-radius: 8px;
		transition:
			border-color 0.3s,
			transform 0.3s;
	}

	.skill img {
		height: 8rem;
		max-width: 90%;
		transition:
			transform 0.3s,
			filter 0.3s;
	}

	.skill p {
		margin-top: 0.75rem;
		font-size: 1.4rem;
		color: #fcccd3;
		transition: color 0.3s;
	}

	.skill:hover {
		border-color: #303030;
		transform: translateY(-4px);
	}

	.skill:hover img {
		filter: brightness(1.1);
		transform: scale(1.05);
	}

	.skill:hover p {
		color: #303030;
	}
</style>
