<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<a
	href="#main-content"
	class="sr-only absolute top-2 left-2 z-50 rounded-lg bg-card-bg px-4 py-3 font-semibold text-heading shadow-lg focus:not-sr-only"
	>Skip to content</a
>

{@render children()}
