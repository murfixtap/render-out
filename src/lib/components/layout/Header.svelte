<script lang="ts">
	import { resolve } from '$app/paths';
	import Logo from '$lib/components/layout/Logo.svelte';
</script>

<header class="border-b border-border-main" id="header">
	<div
		class="mx-auto flex h-20 w-full max-w-7xl items-center justify-between px-4 sm:px-6 md:px-8 lg:px-10"
	>
		<Logo />
		<a
			href={resolve('/pricing')}
			class="rounded-lg bg-accent px-5 py-3.5 font-semibold text-card-bg shadow-[0px_4px_12px_var(--color-accent-shadow)] transition hover:bg-accent-hover"
			>Get Started</a
		>
	</div>
</header>
