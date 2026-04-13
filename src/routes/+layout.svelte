<script lang="ts">
	import { page } from '$app/state';
	import ThemeToggle from '$lib/components/theme/ThemeToggle.svelte';
	import { site } from '$lib/site';
	import './layout.css';

	let { children } = $props();

	const pageTitle = site.name;
	const canonicalUrl = $derived(new URL(page.url.pathname, `${site.url}/`).toString());
</script>

<svelte:head>
	<title>{pageTitle}</title>
	<meta name="description" content={site.description} />
	<link rel="canonical" href={canonicalUrl} />
	<link rel="icon" href="/favicon.ico" sizes="any" />
	<meta property="og:title" content={site.name} />
	<meta property="og:description" content={site.description} />
	<meta property="og:url" content={canonicalUrl} />
</svelte:head>
<div class="pointer-events-none fixed top-4 right-4 z-50 sm:top-6 sm:right-6">
	<div class="pointer-events-auto">
		<ThemeToggle />
	</div>
</div>
{@render children()}
