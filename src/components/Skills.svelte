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
		{ name: "JavaScript", type: "Frontend", file: javascript },
		{ name: "TypeScript", type: "Frontend", file: typescript },
		{ name: "React", type: "Frontend", file: react },
		{ name: "Vue", type: "Frontend", file: vue },
		{ name: "Svelte", type: "Frontend", file: svelte },
		{ name: "Tailwind CSS", type: "Frontend", file: tailwind },
		{ name: "Sass", type: "Frontend", file: sass },
		{ name: "HTML5", type: "Frontend", file: html },
		{ name: "CSS3", type: "Frontend", file: css },

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

<section class="skills">
	<div class="container">
		<h2>Skills</h2>

		{#each categories as category}
			<div class="category">
				<h3>{category}</h3>
				<div class="skills-grid">
					{#each skills.filter((s) => s.type === category) as skill}
						<div class="skill">
							<div class="icon-box">
								<img src={skill.file} alt={skill.name} />
							</div>
							<p class="label">{skill.name}</p>
						</div>
					{/each}
				</div>
			</div>
		{/each}
	</div>
</section>

<style>
	:root {
		--text: #3a2f2f;
		--mauve: #6b4e5c;
		--gold: #ead7a3;
		--ivory: #fff9f5;

		/* shared sizing */
		--icon-h: clamp(56px, 12vw, 80px); /* fixed icon box height */
		--item-h: clamp(120px, 22vw, 160px); /* total item height so labels align */
	}

	section.skills {
		padding: clamp(24px, 5vw, 56px) clamp(12px, 4vw, 40px);
		background: var(--ivory);
	}
	.container {
		max-width: 1280px;
		margin: 0 auto;
	}
	h2 {
		font-family: "Cormorant Garamond", serif;
		font-size: clamp(22px, 3.2vw, 32px);
		margin: 0 0 1rem;
		color: var(--text);
	}
	.category {
		margin-block: clamp(12px, 4vw, 28px);
	}
	.category h3 {
		font-family: "Cormorant Garamond", serif;
		font-size: clamp(18px, 2.6vw, 24px);
		color: var(--mauve);
		margin: 0 0 0.75rem;
		letter-spacing: 0.02em;
		position: relative;
	}
	.category h3::after {
		content: "";
		display: block;
		width: 40px;
		height: 2px;
		background: var(--gold);
		border-radius: 2px;
		margin-top: 6px;
	}

	/* grid: 3-up on modern phones and up; 2-up only below 360px */
	.skills-grid {
		display: grid;
		grid-template-columns: repeat(3, minmax(0, 1fr));
		gap: 16px 12px; /* row/col */
	}
	@media (max-width: 359px) {
		.skills-grid {
			grid-template-columns: repeat(2, minmax(0, 1fr));
		}
	}

	/* equal-height items with bottom-aligned labels */
	.skill {
		min-height: var(--item-h);
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-start;
		padding: 6px 0;
	}

	/* fixed icon box so all labels start at the same baseline */
	.icon-box {
		height: var(--icon-h);
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.icon-box img {
		max-height: 100%;
		width: auto;
		max-width: 90%;
		display: block;
	}

	.label {
		margin-top: auto; /* pushes label to the bottom */
		padding-top: 8px;
		font-size: clamp(12px, 1.5vw, 14px);
		color: var(--text);
		font-weight: 500;
		text-align: center;
		line-height: 1.2;
	}

	/* optional subtle hover nudge on pointers */
	@media (hover: hover) {
		.icon-box img {
			transition: transform 0.15s ease;
		}
		.skill:hover .icon-box img {
			transform: translateY(-2px);
		}
	}
	@media (prefers-reduced-motion: reduce) {
		.icon-box img {
			transition: none;
		}
	}
</style>
