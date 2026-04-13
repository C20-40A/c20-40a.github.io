<script lang="ts">
	import { ArrowRight, Blocks, Globe, Layers3, Sparkles, Zap } from '@lucide/svelte';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import * as Card from '$lib/components/ui/card/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';

	const highlights = [
		{ value: '10x', label: 'faster concept-to-launch cycles' },
		{ value: '3d', label: 'from brief to polished first release' },
		{ value: '100%', label: 'SvelteKit-first delivery' }
	];

	const capabilities = [
		{
			title: 'Launch-ready landing pages',
			description:
				'Message hierarchy, conversion paths, and product visuals tuned for a sharp first impression.',
			icon: Sparkles
		},
		{
			title: 'Design systems that scale',
			description:
				'Reusable sections and UI primitives built on modern SvelteKit patterns instead of one-off markup.',
			icon: Layers3
		},
		{
			title: 'Fast interactions',
			description:
				'Micro-animations, progressive loading, and responsive behavior without turning the page into sludge.',
			icon: Zap
		}
	];

	const features = [
		'Hero sections with stronger visual hierarchy',
		'Reusable feature, pricing, and CTA blocks',
		'Clean shadcn-svelte primitives with Tailwind v4',
		'Built for desktop and mobile from the start'
	];
</script>

<svelte:head>
	<title>C20 | Build a sharper first impression</title>
	<meta
		name="description"
		content="C20 creates sharp, modern landing pages and product websites with SvelteKit and shadcn-svelte."
	/>
</svelte:head>

<div class="relative overflow-hidden">
	<div class="pointer-events-none absolute inset-x-0 top-0 -z-10 h-152 bg-[radial-gradient(circle_at_top,rgba(255,255,255,0.12),transparent_42%),linear-gradient(180deg,rgba(24,24,27,0.18),transparent_72%)]"></div>
	<div class="pointer-events-none absolute left-1/2 top-24 -z-10 h-80 w-80 -translate-x-1/2 rounded-full bg-white/8 blur-3xl"></div>

	<section class="mx-auto flex min-h-screen w-full max-w-7xl items-center px-6 py-24 sm:px-8 lg:px-10">
		<div class="grid w-full gap-12 lg:grid-cols-[1.15fr_0.85fr] lg:items-center">
			<div class="space-y-8">
				<Badge variant="outline" class="rounded-full px-3 py-1 text-[11px] uppercase tracking-[0.24em]">
					SvelteKit landing systems
				</Badge>

				<div class="space-y-6">
					<h1 class="max-w-4xl text-5xl leading-none font-semibold tracking-[-0.06em] text-balance sm:text-6xl lg:text-7xl">
						Launch pages that feel more like products than templates.
					</h1>
					<p class="text-muted-foreground max-w-2xl text-base leading-7 sm:text-lg">
						C20 designs and ships high-clarity landing pages with sharper motion, cleaner
						typography, and stronger conversion structure. Minimal by default, generic by
						never.
					</p>
				</div>

				<div class="flex flex-col gap-3 sm:flex-row">
					<Button href="#contact" size="lg" class="h-11 rounded-full px-5 text-sm">
						Start a project
						<ArrowRight class="size-4" />
					</Button>
					<Button href="#work" variant="outline" size="lg" class="h-11 rounded-full px-5 text-sm">
						See the system
					</Button>
				</div>

				<div class="grid max-w-2xl grid-cols-1 gap-3 pt-2 sm:grid-cols-3">
					{#each highlights as item (item.label)}
						<div class="rounded-3xl border border-border/80 bg-card/70 px-4 py-4 shadow-[0_10px_30px_-24px_rgba(0,0,0,0.7)] backdrop-blur">
							<div class="text-2xl font-semibold tracking-[-0.05em]">{item.value}</div>
							<p class="text-muted-foreground mt-1 text-sm leading-6">{item.label}</p>
						</div>
					{/each}
				</div>
			</div>

			<div class="relative">
				<div class="absolute inset-0 rounded-[2rem] bg-[linear-gradient(135deg,rgba(0,0,0,0.06),transparent_45%,rgba(0,0,0,0.08))] blur-2xl"></div>
				<Card.Root class="relative rounded-[2rem] border-border/80 bg-card/90 p-2 shadow-[0_30px_80px_-30px_rgba(0,0,0,0.55)] backdrop-blur">
					<div class="rounded-[1.4rem] border border-border/80 bg-muted/30 p-6">
						<div class="flex items-center justify-between">
							<div class="flex items-center gap-2">
								<div class="size-2.5 rounded-full bg-zinc-300"></div>
								<div class="size-2.5 rounded-full bg-zinc-300"></div>
								<div class="size-2.5 rounded-full bg-zinc-300"></div>
							</div>
							<Badge variant="secondary" class="rounded-full">Nova + zinc</Badge>
						</div>

						<div class="mt-10 grid gap-4">
							<div class="space-y-3">
								<div class="h-3 w-24 rounded-full bg-zinc-200"></div>
								<div class="h-12 w-full rounded-2xl bg-zinc-950"></div>
								<div class="grid grid-cols-[1.2fr_0.8fr] gap-3">
									<div class="h-24 rounded-3xl bg-white shadow-sm ring-1 ring-zinc-200"></div>
									<div class="h-24 rounded-3xl bg-zinc-100 ring-1 ring-zinc-200"></div>
								</div>
							</div>

							<div class="grid gap-3 sm:grid-cols-3">
								{#each capabilities as item (item.title)}
									{@const Icon = item.icon}
									<div class="rounded-3xl bg-white p-4 ring-1 ring-zinc-200/90">
										<Icon class="size-4 text-zinc-500" />
										<div class="mt-8 h-2 w-20 rounded-full bg-zinc-200"></div>
										<div class="mt-2 h-2 w-16 rounded-full bg-zinc-100"></div>
									</div>
								{/each}
							</div>
						</div>
					</div>
				</Card.Root>
			</div>
		</div>
	</section>

	<section id="work" class="mx-auto w-full max-w-7xl px-6 pb-24 sm:px-8 lg:px-10">
		<div class="grid gap-6 lg:grid-cols-[0.85fr_1.15fr]">
			<Card.Root class="rounded-[2rem] border-border/80 bg-card shadow-[0_20px_80px_-40px_rgba(0,0,0,0.55)]">
				<Card.Header class="px-6 pt-6">
					<Badge class="rounded-full bg-secondary text-secondary-foreground hover:bg-secondary">Approach</Badge>
					<Card.Title class="mt-4 text-3xl tracking-[-0.04em]">
						A cleaner stack for high-signal launch pages
					</Card.Title>
					<Card.Description>
						Use shadcn-svelte for the system, then push the visual direction in layout,
						spacing, contrast, and motion.
					</Card.Description>
				</Card.Header>
				<Card.Content class="px-6 pb-6">
					<div class="grid gap-4">
						{#each features as feature (feature)}
							<div class="flex items-center gap-3 rounded-2xl border border-border bg-muted/30 px-4 py-3">
								<Blocks class="size-4 text-muted-foreground" />
								<span class="text-sm">{feature}</span>
							</div>
						{/each}
					</div>
				</Card.Content>
			</Card.Root>

			<div class="grid gap-6 md:grid-cols-3">
				{#each capabilities as item (item.title)}
					{@const Icon = item.icon}
					<Card.Root class="rounded-[2rem] border-border/80 bg-card/90 shadow-[0_12px_40px_-24px_rgba(0,0,0,0.4)] backdrop-blur">
						<Card.Header class="px-6 pt-6">
							<div class="flex size-11 items-center justify-center rounded-2xl border border-border bg-muted/40">
								<Icon class="size-5 text-muted-foreground" />
							</div>
							<Card.Title class="pt-4 text-xl tracking-[-0.03em]">{item.title}</Card.Title>
						</Card.Header>
						<Card.Content class="text-muted-foreground px-6 pb-6 text-sm leading-6">
							{item.description}
						</Card.Content>
					</Card.Root>
				{/each}
			</div>
		</div>
	</section>

	<section class="mx-auto w-full max-w-7xl px-6 pb-24 sm:px-8 lg:px-10">
		<Card.Root class="rounded-[2rem] border-border/80 bg-card/90 shadow-[0_18px_70px_-42px_rgba(0,0,0,0.4)] backdrop-blur">
			<Card.Content class="grid gap-8 px-6 py-8 lg:grid-cols-[1fr_auto_1fr] lg:items-center">
				<div class="space-y-3">
					<p class="text-muted-foreground text-sm uppercase tracking-[0.22em]">Stack</p>
					<div class="flex flex-wrap gap-2">
						<Badge variant="outline" class="rounded-full">SvelteKit</Badge>
						<Badge variant="outline" class="rounded-full">shadcn-svelte</Badge>
						<Badge variant="outline" class="rounded-full">Tailwind v4</Badge>
						<Badge variant="outline" class="rounded-full">Lucide</Badge>
					</div>
				</div>

				<Separator orientation="vertical" class="hidden h-14 lg:block" />
				<Separator class="lg:hidden" />

				<div class="flex items-center justify-between gap-6">
					<div>
						<p class="text-muted-foreground text-sm uppercase tracking-[0.22em]">Outcome</p>
						<p class="text-muted-foreground mt-2 max-w-md text-sm leading-6">
							A reusable base you can keep extending instead of redesigning every section from
							scratch.
						</p>
					</div>
					<Globe class="hidden size-10 text-zinc-300 sm:block" />
				</div>
			</Card.Content>
		</Card.Root>
	</section>

	<section id="contact" class="mx-auto w-full max-w-5xl px-6 pb-28 text-center sm:px-8">
		<div class="space-y-6 rounded-[2rem] border border-border/80 bg-card/90 px-6 py-12 shadow-[0_18px_70px_-42px_rgba(0,0,0,0.45)] backdrop-blur sm:px-10">
			<Badge variant="secondary" class="rounded-full">Ready to ship</Badge>
			<h2 class="text-4xl leading-none font-semibold tracking-[-0.05em] text-balance sm:text-5xl">
				If the current page feels generic, rebuild the first impression.
			</h2>
			<p class="text-muted-foreground mx-auto max-w-2xl text-sm leading-7 sm:text-base">
				The system is installed. The next step is replacing placeholder sections with your real
				product narrative, proof, and conversion flow.
			</p>
			<div class="flex flex-col justify-center gap-3 sm:flex-row">
				<Button href="mailto:hello@c20.dev" size="lg" class="h-11 rounded-full px-5">
					Contact C20
				</Button>
				<Button href="https://github.com/c20-40a" variant="outline" size="lg" class="h-11 rounded-full px-5">
					View GitHub
				</Button>
			</div>
		</div>
	</section>
</div>
