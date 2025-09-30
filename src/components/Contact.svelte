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
			.then((_) => {
				if (!voiceOfGod) {
					formSuccess = true;
					setTimeout(() => {
						formSuccess = false;
					}, 5000);
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
	<div class="voice-of-god">
		<h2>
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
	<div class="form-success">
		<h6>Email has been sent!</h6>
	</div>
{/if}
<section>
	<div class="container">
		<h2>Contact</h2>
		<p>
			Let's build something together. I'm currently available for freelance
			contracts — remote, hybrid, or in-person across the Greater Toronto Area
			and Simcoe County. Whether you need a web app, esports tool, or custom
			API, reach out below.
		</p>
		<div class="grid-container">
			<div>
				<p class="email">Email: hello@catielanier.ca</p>
				{#if !isKr}
					<p>Prefer to talk directly?</p>
					<p>
						<a
							href="https://calendly.com/catielanier/30min"
							target="_blank"
							rel="noopener noreferrer"
							class="calendly"
						>
							Schedule a free call with me
						</a>.
					</p>
				{/if}

				<div class="contact-gap">
					<div>
						<a
							href="https://github.com/catielanier"
							target="_blank"
							rel="noopener noreferrer"
						>
							<img src={github} alt="Github" />
						</a>
					</div>
					<div>
						<a
							href="https://linkedin.com/in/catielanier"
							target="_blank"
							rel="noopener noreferrer"
						>
							<img src={linkedin} alt="LinkedIn" />
						</a>
					</div>
					<div>
						<a
							href="https://instagram.com/ohohcatie"
							target="_blank"
							rel="noopener noreferrer"
						>
							<img src={instagram} alt="Instagram" />
						</a>
					</div>
					<div>
						<a
							href="https://fiverr.com/catie_lanier"
							target="_blank"
							rel="noopener noreferrer"
						>
							<img src={fiverr} alt="Fiverr" />
						</a>
					</div>
				</div>
			</div>
			<div>
				{#if !isKr}
					<form on:submit|preventDefault={validateMessage}>
						<input
							type="text"
							name="name"
							bind:value={name}
							required
							placeholder="Your name"
						/>
						<input
							type="email"
							name="email"
							bind:value={email}
							required
							placeholder="Email address"
						/>
						<textarea
							placeholder="Tell me about your project (scope, timeline, goals)"
							name="message"
							bind:value={message}
							required
							cols="30"
							rows="10"
						/>
						<input type="hidden" name="ip" bind:value={ip} />
						<input
							type="hidden"
							name="voice of god activated"
							bind:value={voiceOfGod}
						/>
						<button type="submit">
							<span />
							<span />
							<span />
							<span />
							Send email
						</button>
					</form>
				{/if}
			</div>
		</div>
	</div>
</section>

<style>
	section {
		background: #fdecef;
	}

	.container {
		max-width: 1280px;
		margin: 0 auto;
	}
	.voice-of-god {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		width: 100%;
		height: 100vh;
		background: black;
		color: white;
		z-index: 999;
	}
	.voice-of-god h2 {
		font-size: 3.8rem;
	}
	.form-success {
		z-index: 25;
		position: fixed;
		bottom: 100px;
		left: 50%;
		transform: translateX(-50%);
		background-color: #c28485;
		color: white;
		padding: 5px 10px;
		border-radius: 5px;
	}
	.form-success h6 {
		margin: 0;
		font-size: 1.8rem;
		font-family: "Arvo", serif;
	}
	.grid-container {
		display: grid;
		grid-template-columns: 1fr 1fr;
	}
	.email {
		font-family: "Comfortaa", sans-serif;
		font-size: 1.7rem;
		margin-top: 35px;
	}
	.contact-gap {
		margin-top: 35px;
		max-width: 225px;
		width: 100%;
		display: grid;
		grid-template-columns: repeat(5, 1fr);
		grid-gap: 20px;
	}
	.contact-gap div img {
		width: 100%;
	}
	input,
	textarea {
		width: 100%;
		background: #fff9f5;
		color: #3a2f2f;
		border: 0;
		border-radius: 5px;
		padding: 14px 16px;
		outline: none;
		border: 1px solid #c9c6d9;
		font-family: "Arvo", serif;
		font-size: 1.8rem;
		box-shadow: 0 1px 0 rgba(0, 0, 0, 0.02) inset;
		transition: 0.5 all ease-in-out;
	}
	input:focus,
	textarea:focus {
		outline: none;
		border: 1px solid #e5a4b3;
	}
	input:focus-visible,
	textarea:focus-visible {
		border-color: var(--pink);
		box-shadow: 0 0 0 3px color-mix(in oklab, #ead7a3 60%, transparent);
		outline: none;
		background: white;
	}
	input::placeholder,
	textarea::placeholder {
		color: color-mix(in oklab, #3a2f2f 55%, white);
	}

	button {
		cursor: pointer;
		margin-top: 15px;
		position: relative;
		padding: 15px 20px;
		background: #fdecef;
		font-family: "Comfortaa", serif;
		text-transform: uppercase;
		font-size: 1.6rem;
		border-radius: 10px;
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
		border-top-right-radius: 0px;
		border-bottom-left-radius: 0px;
		border-top-right-radius: 10px;
		border-bottom-left-radius: 10px;
		color: #e5a4b3;
	}
	button:hover:before,
	button:hover:after {
		width: 100%;
		height: 100%;
		border-bottom-left-radius: 10px;
		border-top-right-radius: 10px;
	}
	button:hover:before {
		border-bottom-color: #ead7a3;
		border-right-color: #ead7a3;
	}
	button:hover:after {
		border-top-color: #ead7a3;
		border-left-color: #ead7a3;
	}

	textarea {
		resize: none;
	}

	a.calendly {
		text-decoration: underline;
		color: #c28485; /* your rose accent — darker, readable */
		transition: color 0.2s ease-in-out;
	}

	a.calendly:hover {
		color: #f7a3b4; /* lighter pink on hover */
	}

	@media (max-width: 424px) {
		.grid-container {
			grid-template-columns: 1fr;
			grid-template-rows: 1fr 2fr;
			grid-gap: 0;
		}
	}
</style>
