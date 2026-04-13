<script lang="ts">
	import { onMount } from "svelte";
	import { Button } from "$lib/components/ui/button";

	let isDark = $state(false);

	const syncTheme = () => {
		isDark = document.documentElement.classList.contains("dark");
	};

	const toggleTheme = () => {
		isDark = !isDark;
		document.documentElement.classList.toggle("dark", isDark);
	};

	onMount(() => {
		syncTheme();
	});
</script>

<Button
	variant="outline"
	size="icon"
	class="rounded-full"
	aria-label={isDark ? "Switch to light theme" : "Switch to dark theme"}
	onclick={toggleTheme}
>
	<span class="theme-toggle-icon" class:is-dark={isDark} aria-hidden="true">
		<svg
			class="theme-icon theme-icon-moon h-6 w-6 fill-current"
			xmlns="http://www.w3.org/2000/svg"
			viewBox="0 0 24 24"
			aria-hidden="true"
		>
			<path d="M21.64,13a1,1,0,0,0-1.05-.14,8.05,8.05,0,0,1-3.37.73A8.15,8.15,0,0,1,9.08,5.49a8.59,8.59,0,0,1,.25-2A1,1,0,0,0,8,2.36,10.14,10.14,0,1,0,22,14.05,1,1,0,0,0,21.64,13Zm-9.5,6.69A8.14,8.14,0,0,1,7.08,5.22v.27A10.15,10.15,0,0,0,17.22,15.63a9.79,9.79,0,0,0,2.1-.22A8.11,8.11,0,0,1,12.14,19.73Z" />
		</svg>
		<svg
			class="theme-icon theme-icon-sun h-6 w-6 fill-current"
			xmlns="http://www.w3.org/2000/svg"
			viewBox="0 0 24 24"
			aria-hidden="true"
		>
			<path d="M5.64,17l-.71.71a1,1,0,0,0,0,1.41,1,1,0,0,0,1.41,0l.71-.71A1,1,0,0,0,5.64,17ZM5,12a1,1,0,0,0-1-1H3a1,1,0,0,0,0,2H4A1,1,0,0,0,5,12Zm7-7a1,1,0,0,0,1-1V3a1,1,0,0,0-2,0V4A1,1,0,0,0,12,5ZM5.64,7.05a1,1,0,0,0,.7.29,1,1,0,0,0,.71-.29,1,1,0,0,0,0-1.41l-.71-.71A1,1,0,0,0,4.93,6.34Zm12,.29a1,1,0,0,0,.7-.29l.71-.71a1,1,0,1,0-1.41-1.41L17,5.64a1,1,0,0,0,0,1.41A1,1,0,0,0,17.66,7.34ZM21,11H20a1,1,0,0,0,0,2h1a1,1,0,0,0,0-2Zm-9,8a1,1,0,0,0-1,1v1a1,1,0,0,0,2,0V20A1,1,0,0,0,12,19ZM18.36,17A1,1,0,0,0,17,18.36l.71.71a1,1,0,0,0,1.41,0,1,1,0,0,0,0-1.41ZM12,6.5A5.5,5.5,0,1,0,17.5,12,5.51,5.51,0,0,0,12,6.5Zm0,9A3.5,3.5,0,1,1,15.5,12,3.5,3.5,0,0,1,12,15.5Z" />
		</svg>
	</span>
</Button>

<style>
	.theme-toggle-icon {
		position: relative;
		display: inline-grid;
		place-items: center;
		width: 1.5rem;
		height: 1.5rem;
	}

	.theme-icon {
		position: absolute;
		top: 50%;
		left: 50%;
		transform-origin: center;
		transition:
			transform 360ms cubic-bezier(0.22, 1, 0.36, 1),
			opacity 220ms ease;
		will-change: transform, opacity;
	}

	.theme-icon-moon {
		opacity: 0;
		transform: translate(-50%, -50%) rotate(-150deg) scale(0.45);
	}

	.theme-icon-sun {
		opacity: 1;
		transform: translate(-50%, -50%) rotate(0deg) scale(1);
	}

	.theme-toggle-icon.is-dark .theme-icon-moon {
		opacity: 1;
		transform: translate(-50%, -50%) rotate(0deg) scale(1);
	}

	.theme-toggle-icon.is-dark .theme-icon-sun {
		opacity: 0;
		transform: translate(-50%, -50%) rotate(150deg) scale(0.45);
	}

	@media (prefers-reduced-motion: reduce) {
		.theme-icon {
			transition:
				opacity 120ms linear,
				transform 120ms linear;
		}

		.theme-icon-moon,
		.theme-toggle-icon.is-dark .theme-icon-sun {
			transform: translate(-50%, -50%) scale(0.9);
		}
	}
</style>
