<script lang="ts">
	import { page } from '$app/state';
	import { home, site } from '$lib/site';
	import './layout.css';

	let { children } = $props();

	const pageTitle = `${home.title} | ${site.name}`;
	const canonicalUrl = $derived(new URL(page.url.pathname, `${site.url}/`).toString());
	const jsonLd = JSON.stringify({
		'@context': 'https://schema.org',
		'@type': 'WebSite',
		name: site.name,
		url: site.url,
		description: site.description
	});
</script>

<svelte:head>
	<title>{pageTitle}</title>
	<meta name="description" content={site.description} />
	<link rel="canonical" href={canonicalUrl} />
	<link rel="icon" href="/favicon.ico" sizes="any" />
	<meta property="og:type" content="website" />
	<meta property="og:site_name" content={site.name} />
	<meta property="og:title" content={pageTitle} />
	<meta property="og:description" content={site.description} />
	<meta property="og:url" content={canonicalUrl} />
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:title" content={pageTitle} />
	<meta name="twitter:description" content={site.description} />
	<script type="application/ld+json">
		{jsonLd}
	</script>
</svelte:head>
{@render children()}
