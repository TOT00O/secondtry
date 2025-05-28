<script>
	import '../app.postcss';

	// Highlight JS
	import hljs from 'highlight.js/lib/core';
	import 'highlight.js/styles/github-dark.css';
	import { storeHighlightJs } from '@skeletonlabs/skeleton';
	import xml from 'highlight.js/lib/languages/xml'; // for HTML
	import css from 'highlight.js/lib/languages/css';
	import javascript from 'highlight.js/lib/languages/javascript';
	import typescript from 'highlight.js/lib/languages/typescript';

	hljs.registerLanguage('xml', xml); // for HTML
	hljs.registerLanguage('css', css);
	hljs.registerLanguage('javascript', javascript);
	hljs.registerLanguage('typescript', typescript);
	storeHighlightJs.set(hljs);

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });

	import { base } from '$app/paths';
	let lastScrollTop //last scroll position
	let showNav = true
	
	import { scrollTo, scrollRef, scrollTop } from 'svelte-scrolling'
	import { page } from '$app/stores';

  $: isHome = $page.url.pathname === '/' ;
</script>

<svelte:window on:scroll={()=>{
	var st = window.pageYOffset || document.documentElement.scrollTop; //Get current scroll position
	//If new scroll position is greater than old (previous/ last) - hide
	if (st > lastScrollTop) 
   showNav = false
  else 
  showNav = true
  lastScrollTop = st;

}}></svelte:window>




<nav class="nav {showNav == true? "show": "hide" }">
{#if isHome}

	<a href="{base}/" use:scrollTo={'home'}>Home</a>
	<a href="{base}/#about" use:scrollTo={'about'}>About</a>
	<a href="{base}/#art" use:scrollTo={'art'}>Art</a>
	<a href="{base}/#projects" use:scrollTo={'projects'} >Projects</a>
	<a href="{base}/devblog">Devblog</a>
	{:else}
	<a href="{base}/">Home</a>
	<a href="{base}/#about">About</a>
	<a href="{base}/#art"np>Art</a>
	<a href="{base}/#projects" >Projects</a>
	<a href="{base}/devblog">Devblog</a>
	{/if}
	
	
</nav>


<slot />

<style>
		.nav{
		background-color: rgb(255, 255, 255);
		padding: 6px;
		position: fixed;
		top: 0;
		width: 100%;
		z-index: 200;
		color: black;
		
	}

			.nav:hover{
		background-color: rgb(0, 0, 0);
		padding: 6px;
		position: fixed;
		top: 0;
		width: 100%;
		z-index: 200;
		opacity: 1;
		color: white;
	}

	.nav a:hover{
		text-decoration: overline;
	}

		.hide{
		opacity: 0;
		transition: 0.3s ease-out;
	}
	.show {
		opacity: 1 ;
		transition: 0.3s ease-in;
	}


	
</style>