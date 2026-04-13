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
				class="inline-flex items-center justify-center transition-opacity hover:opacity-70"
				aria-label="Open C20 GitHub profile"
				target="_blank"
				rel="noreferrer"
			>
				<img
					src="/github.svg"
					alt="GitHub"
					class="h-10 w-10 dark:invert"
				/>
			</a>
		</p>
	</div>
</section>
