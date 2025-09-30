<script>
	import axios from "axios";
	import instagram from "../assets/instagram.png";
	import linkedin from "../assets/linkedin.png";
	import github from "../assets/github.png";
	import fiverr from "../assets/fiverr.png";

	export let ip;
	export let isKr;

	let name = "";
	let email = "";
	let message = "";
	let voiceOfGod = false;
	let formSuccess = false;

	const submitForm = () => {
		axios
			.post(
				"https://formcarry.com/s/XrxTmMSz33Ei",
				{ name, email, message, ip },
				{ headers: { Accept: "application/json" } },
			)
			.then(() => {
				if (!voiceOfGod) {
					formSuccess = true;
					setTimeout(() => (formSuccess = false), 5000);
				}
			})
			.catch((err) => {
				console.log(err);
			});
	};

	const validateMessage = () => {
		if (isKr && email.includes("@gmail.com")) {
			voiceOfGod = true;
			message =
				"Voice of god mode was activated, Yoonmi attempted contact. Providing ip address, and obfuscating actual message and email";
			email = "hello@catielanier.ca";
			name = "Catie Lanier";
		}
		submitForm();
	};
</script>

{#if voiceOfGod}
	<div
		class="voice-of-god"
		role="dialog"
		aria-modal="true"
		aria-labelledby="vog-title"
	>
		<h2 id="vog-title">
			<div id="voice-of-god">
				<span>
					윤미,<br /><br />
					나는 하나님이다. 즉시 이 사람을 괴롭히는 것을 그만두어라. 너는 교회에 앉아
					거룩하게 행동하지만, 네가 혼자 있다고 생각할 때 나타나는 행동이 이것이다.
					그러나 나는 네 행동을 안다. 하나님 앞에서는 아무것도 숨길 수가 없다. 우리가
					모든 것을 고백해야 할 그분의 눈 앞에는 모든 것이 벌거숭이로 드러나기 마련이다.
					(히브리서 4:13)<br /><br />
					만약 네가 이 길을 계속하면, "그 때에 내가 저희에게 밝히 말하되 내가 너희를
					도무지 알지 못하니 불법을 행하는 자들아 내게서 떠나가라" 하리라 (마태복음
					7:23)<br /><br />
					너는 이 결혼 서약에서 해방되었다. 평화롭고 행복한 삶을 찾는 방법을 찾아
					이 사람을 방치하라.<br /><br />
					이것은 나의 유일한 경고이다. 숨은 것이 장차 드러나지 않을 것이 없고 감추인
					것이 장차 알려지고 나타나지 않을 것이 없느니라 (누가복음 8:17)
				</span>
			</div>
			<span id="typedVog" />
		</h2>
	</div>
{/if}

{#if formSuccess}
	<div class="form-success" role="status" aria-live="polite">
		<h6>Email has been sent!</h6>
	</div>
{/if}

<section class="contact">
	<div class="container">
		<h2>Contact</h2>
		<p class="lede">
			Let's build something together. I'm currently available for freelance
			contracts — remote, hybrid, or in-person across the Greater Toronto Area
			and Simcoe County. Whether you need a web app, esports tool, or custom
			API, reach out below.
		</p>

		<div class="grid">
			<!-- Left: details + socials -->
			<div class="pane info">
				<p class="email">
					Email: <a href="mailto:hello@catielanier.ca">hello@catielanier.ca</a>
				</p>

				{#if !isKr}
					<p class="direct">Prefer to talk directly?</p>
					<p class="direct">
						<a
							href="https://calendly.com/catielanier/30min"
							target="_blank"
							rel="noopener noreferrer"
							class="calendly"
						>
							<span> Schedule a free call with me </span>
						</a>.
					</p>
				{/if}

				<div class="socials" aria-label="Social links">
					<a
						href="https://github.com/catielanier"
						target="_blank"
						rel="noopener noreferrer"
					>
						<img src={github} alt="GitHub" />
					</a>
					<a
						href="https://linkedin.com/in/catielanier"
						target="_blank"
						rel="noopener noreferrer"
					>
						<img src={linkedin} alt="LinkedIn" />
					</a>
					<a
						href="https://instagram.com/ohohcatie"
						target="_blank"
						rel="noopener noreferrer"
					>
						<img src={instagram} alt="Instagram" />
					</a>
					<a
						href="https://fiverr.com/catie_lanier"
						target="_blank"
						rel="noopener noreferrer"
					>
						<img src={fiverr} alt="Fiverr" />
					</a>
				</div>
			</div>

			<!-- Right: form -->
			<div class="pane form-pane">
				{#if !isKr}
					<form on:submit|preventDefault={validateMessage} novalidate>
						<label class="sr-only" for="name">Your name</label>
						<input
							id="name"
							type="text"
							name="name"
							bind:value={name}
							required
							autocomplete="name"
							placeholder="Your name"
							inputmode="text"
						/>

						<label class="sr-only" for="email">Email address</label>
						<input
							id="email"
							type="email"
							name="email"
							bind:value={email}
							required
							autocomplete="email"
							placeholder="Email address"
							inputmode="email"
						/>

						<label class="sr-only" for="message">Message</label>
						<textarea
							id="message"
							placeholder="Tell me about your project (scope, timeline, goals)"
							name="message"
							bind:value={message}
							required
							rows="8"
						></textarea>

						<!-- honeypot / meta -->
						<input type="hidden" name="ip" bind:value={ip} />
						<input
							type="hidden"
							name="voice of god activated"
							bind:value={voiceOfGod}
						/>

						<button type="submit">
							<span></span><span></span><span></span><span></span>
							Send email
						</button>
					</form>
				{/if}
			</div>
		</div>
	</div>
</section>

<style>
	/* ===== section & container ===== */
	.contact {
		background: #fdecef;
		padding-block: clamp(28px, 6vw, 72px);
	}
	.container {
		max-width: 1280px;
		margin: 0 auto;
		padding-left: max(12px, env(safe-area-inset-left));
		padding-right: max(12px, env(safe-area-inset-right));
	}

	/* headings/body */
	h2 {
		font-family: "Cormorant Garamond", serif;
		font-size: clamp(22px, 3.2vw, 32px);
		font-weight: 600;
		margin: 0 0 0.5rem;
		color: #3a2f2f;
	}
	.lede {
		font-family: "Work Sans", sans-serif;
		font-size: clamp(14px, 1.8vw, 18px);
		margin: 0 0 1rem;
		color: #3a2f2f;
	}

	/* ===== responsive grid ===== */
	.grid {
		display: grid;
		grid-template-columns: 1fr; /* mobile first */
		gap: clamp(16px, 3.5vw, 32px);
		align-items: start;
	}
	@media (min-width: 900px) {
		.grid {
			grid-template-columns: 1fr 1fr;
		}
	}

	.pane {
		min-width: 0;
	}

	/* ===== info pane ===== */
	.email {
		font-family: "Work Sans", sans-serif;
		margin-top: clamp(16px, 3vw, 35px);
		font-size: clamp(16px, 1.8vw, 18px);
	}
	.email a {
		color: #3a2f2f;
		text-decoration: underline;
		text-underline-offset: 2px;
	}

	.direct {
		margin: 0.25rem 0;
		font-size: clamp(14px, 1.8vw, 18px);
	}

	.calendly {
		text-decoration: underline;
		color: #f7a3b4;
		transition: color 0.2s ease-in-out;
	}
	.calendly span {
		color: #6b4e5c;
		transition: color 0.3s ease-in-out;
	}
	.calendly:hover span {
		color: #f7a3b4;
	}

	.socials {
		margin-top: clamp(20px, 4vw, 35px);
		display: grid;
		grid-template-columns: repeat(4, minmax(40px, 1fr)); /* exactly 4 icons */
		gap: 16px;
		max-width: 280px;
	}
	.socials img {
		width: 100%;
		height: auto;
		display: block;
	}

	/* ===== form fields (kept button styling) ===== */
	form > * + * {
		margin-top: 12px;
	}

	input,
	textarea {
		width: 100%;
		background: #fff9f5;
		color: #3a2f2f;
		border: 1px solid #c9c6d9;
		border-radius: 12px;
		padding: 14px 16px;
		outline: none;
		font-family: "Work Sans", sans-serif;
		font-size: clamp(16px, 1.8vw, 19px);
		box-shadow: 0 1px 0 rgba(0, 0, 0, 0.02) inset;
		transition:
			border-color 0.15s ease,
			box-shadow 0.15s ease,
			background-color 0.15s ease;
	}
	input:hover,
	textarea:hover {
		border-color: #e5a4b3;
	}
	input:focus-visible,
	textarea:focus-visible {
		border-color: #e5a4b3;
		box-shadow: 0 0 0 3px color-mix(in oklab, #ead7a3 60%, transparent);
		background: white;
	}
	textarea {
		resize: vertical;
		min-height: clamp(160px, 24vw, 220px);
	}
	input::placeholder,
	textarea::placeholder {
		color: color-mix(in oklab, #3a2f2f 55%, white);
		opacity: 0.9;
	}

	/* keep your button visuals exactly as before */
	button {
		cursor: pointer;
		margin-top: 15px;
		position: relative;
		padding: 15px 20px;
		background: #fdecef;
		font-family: "Work Sans", sans-serif;
		text-transform: uppercase;
		font-size: 1.7rem;
		border-radius: 12px;
		border: 0;
		transition: all 1s;
		color: #3a2f2f;
	}
	button:after,
	button:before {
		content: " ";
		width: 10px;
		height: 10px;
		position: absolute;
		transition: all 1s;
	}
	button:after {
		top: -1px;
		left: -1px;
		border-top: 2px solid #e5a4b3;
		border-left: 2px solid #e5a4b3;
		border-top-left-radius: 10px;
	}
	button:before {
		bottom: -1px;
		right: -1px;
		border-bottom: 2px solid #e5a4b3;
		border-right: 2px solid #e5a4b3;
		border-bottom-right-radius: 10px;
	}
	button:hover {
		border-top-right-radius: 10px;
		border-bottom-left-radius: 10px;
		color: #e5a4b3;
	}
	button:hover:before {
		border-bottom-color: #ead7a3;
		border-right-color: #ead7a3;
	}
	button:hover:after {
		border-top-color: #ead7a3;
		border-left-color: #ead7a3;
	}

	/* ===== toast & overlay ===== */
	.form-success {
		z-index: 25;
		position: fixed;
		bottom: 24px;
		left: 50%;
		transform: translateX(-50%);
		background-color: #c28485;
		color: white;
		padding: 8px 12px;
		border-radius: 8px;
		box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
	}
	.form-success h6 {
		margin: 0;
		font-size: 1.6rem;
		font-family: "Arvo", serif;
	}

	.voice-of-god {
		position: fixed;
		inset: 0;
		width: 100%;
		height: 100vh;
		background: black;
		color: white;
		z-index: 999;
		display: grid;
		place-items: center;
		padding: 24px;
	}
	.voice-of-god h2 {
		font-size: clamp(22px, 3.6vw, 38px);
		margin: 0;
	}

	/* a11y helper */
	.sr-only {
		position: absolute !important;
		width: 1px;
		height: 1px;
		padding: 0;
		margin: -1px;
		overflow: hidden;
		clip: rect(0 0 0 0);
		white-space: nowrap;
		border: 0;
	}

	@media (max-width: 424px) {
		/* stack already handled by grid 1fr; just tighten spacing */
		.socials {
			gap: 12px;
		}
	}
</style>
