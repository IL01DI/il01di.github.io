<script lang="ts">
import type { Project } from "src/commons";
import Skull from './Skull.svelte'
	export let proj: Project

	let hasIcon = true;

	if(typeof proj.icon === "undefined") {
		hasIcon = false;
	}


</script>

<main class="card" style="{typeof proj.bg_color !== "undefined" ? `background-color: ${proj.bg_color}; ` : ''}color: {proj.color}">
	<a class="header" href={proj.link} style="color: {proj.color}" target="_blank" rel="noreferrer">
		<div class="banner">
			{#if hasIcon}
				<img class="icon" src={proj.icon} alt="{proj.name} icon" />
			{:else}
				<Skull />
			{/if}
		</div>
	
		
		
	</a>
	<div class="footer">
		<div class="name">{proj.name}</div>
		<div class="desc">{proj.desc}</div>
	</div>
</main>

<style>

main.card {
 display:block;
 background:#fff;
 border-radius:0.5rem;
 overflow:hidden;
 position:relative;
 color:#000;
 height:10rem;
 box-shadow: 0px 0px 50px rgba(0, 0, 0, 0.02);
}
main.card a {
 text-decoration:none;
 color:#000

}
main.card .header {
 width:100%;
 height:100%;
}
main.card .header .banner {
  display:flex;
   align-items:center;
   justify-content:center;
   width: 100%;
  height: 80%;
}
main.card .header .banner .icon {
 width:4rem;
}





main.card .footer {
 position:absolute;
 bottom:0;
 padding:1rem;
 left:0;
 right:0;

}
main.card .footer .name {
 font-size:1rem;
 font-weight:800;

}
main.card .footer .desc {
 font-size:0.8rem;
 opacity:0.7;

}

@media(prefers-color-scheme: dark) {
	main.card {
		background-color: rgb(20, 20, 20);
		color: white;
	}


}


</style>