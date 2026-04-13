<svelte:head>
	<title>C20</title>
	<meta name="description" content="C20 GitHub account landing page." />
</svelte:head>

<script lang="ts">
	const githubUrl = 'https://github.com/C20-40A';
</script>

<section
	class="flex min-h-screen items-center justify-center px-6 py-16"
	aria-label="C20 landing page"
>
	<div class="w-full max-w-xl text-center">
		<h1 class="text-5xl font-semibold tracking-[-0.08em] sm:text-6xl">C20</h1>
		<p class="mt-8">
			<a
				href={githubUrl}
				class="text-lg underline decoration-1 underline-offset-4 transition-opacity hover:opacity-70"
			>
				GitHub
			</a>
		</p>
	</div>
</section>
