<script>
	import {inject} from '@vercel/analytics';
	import MenuBar from "./components/MenuBar.svelte";
	import Header from "./components/Header.svelte";
	import Skills from "./components/Skills.svelte";
	import Portfolio from "./components/Portfolio.svelte";
	import Contact from "./components/Contact.svelte";
	import Footer from "./components/Footer.svelte";
	// import Blog from "./components/Blog.svelte";
	import { onMount } from "svelte";
	import axios from "axios";
	import { COUNTRIES } from "./utils/constants";
	import Divider from "./components/Divider.svelte";
	let posts = [];
	let ip;
	let isKr;
	const retrieveBlogPosts = async () => {
		const posts = [];
		try {
			const res = await axios(
				"https://protected-atoll-04619.herokuapp.com/api/posts/",
			);
			res.data.data.forEach((item) => {
				posts.push(item);
			});
			return posts;
		} catch {
			return posts;
		}
	};
	const retrieveLocationData = async () => {
		const res = await axios.get(
			"https://api.ipgeolocation.io/ipgeo?apiKey=54de6cf316574fa59a6580f75133b847",
		);
		return { ipAddress: res.data.ip, countryCode: res.data.country_code2 };
	};
	onMount(async () => {
		inject();
		const blogPosts = await retrieveBlogPosts();

		const { ipAddress, countryCode } = await retrieveLocationData();

		posts = blogPosts;
		ip = ipAddress;
		isKr = COUNTRIES.includes(countryCode);
	});
</script>

<div class="container">
	<MenuBar />
	<Header />
	<main>
		<Divider anchorId="skills" />
		<Skills />
		<Divider anchorId="portfolio" />
		<Portfolio />
		<!-- <Divider anchorId="blog" /> -->
		<!-- <Blog {posts} /> -->
		<Divider anchorId="contact" />
		<Contact {ip} {isKr} />
	</main>
</div>
<Footer />

<style>
	.container {
		width: 100%;
		margin: 0 auto;
	}

	@media (max-width: 1280px) {
		.container {
			width: 90%;
		}
	}
</style>
