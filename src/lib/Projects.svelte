<script lang="ts">
import type { Project } from "src/commons";
import ProjectCard from "./ProjectCard.svelte";

// icons
import ipacandy from '../assets/icons/ipacandy.png?url'
import glacier from '../assets/icons/glacier.png?url'


	let projects: Project[] = [
		{
			name: "Glacier",
			icon: glacier,
			link: "https://glcr.app",
			desc: "A non-jailbreak theming platform.",
			bg_color: "#3478f7",
			color: "#fff"
		},
		{
			name: "iPACandy",
			icon: ipacandy,
			link: "https://ipacandy.com",
			desc: "An IPA Library to put you at ease.",
			bg_color: "#FF2370",
			color: "#fff"
		},
		{
			name: "IPA Installer",
			link: "https://s0n1c.ca/ipa-installer/",
			desc: "Install IPAs from any URL."
		},
		{
			name: "IPSWInfo",
			link: "https://s0n1c.ca/ipswinfo",
			desc: "A way to find and download IPSW files."
		},
		{
			name: "iDevice Info",
			link: "https://s0n1c.ca/idevice-info",
			desc: "Retrieve useful information about your iOS/iPadOS device."
		},
		{
			name: "Webclip Maker",
			link: "https://s0n1c.ca/webclip-maker/",
			desc: "A site for creating webclips with ease."
		},
		{
			name: "UDID Fetcher",
			link: "https://github.com/itss0n1c/udid-fetcher",
			desc: "An ExpressJS middleware for fetching iOS device info."
		}
	]

</script>

<main>
	<div class="title">Projects</div>
	<div class="cards">
		{#each projects as proj}
			<ProjectCard proj={proj}></ProjectCard>
		{/each}
		
	</div>
</main>

<style>
	main {
		padding: 2rem 10rem;
		background: #fcfcfc;
	}

	main .title {
		font-size: 1.5rem;
		font-weight: 800;
		margin-bottom: 2rem;
	}

	.cards {
		display: grid;
		grid-gap: 1rem;
		grid-template-columns: repeat(3,1fr);
	}

	@media only screen and (max-width:1230px) {
		.cards {
			grid-template-columns: repeat(2, 1fr);
		}
	}


	@media only screen and (max-width:920px) {
		.cards {
			grid-template-columns: 1fr;
		}
	}

	@media only screen and (max-width:850px) {
		main {
			padding: 2rem 2rem;
		}

	}
	

	@media(prefers-color-scheme: dark) {
		main {
			color: white;
			background: #181818;
		}
	}
</style>