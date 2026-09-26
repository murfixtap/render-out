<script lang="ts">
	import { resolve } from '$app/paths';

	type Props = {
		title: string;
		description?: string;
		backLabel?: string;
	};

	let {
		title,
		description = 'Page under construction.',
		backLabel = 'Back to Main Page'
	}: Props = $props();
</script>

<main class="mx-auto flex w-full max-w-7xl flex-col gap-12 px-4 py-24 sm:px-6 md:px-8 lg:px-10">
	<section>
		<h1 class="font-outfit text-4xl font-extrabold text-heading">{title}</h1>
		<p class="mt-4 text-text-primary">{description}</p>
	</section>

	<a
		href={resolve('/')}
		class="w-fit rounded-lg bg-accent px-5 py-3.5 font-semibold text-card-bg shadow-[0px_4px_12px_#2563eb33] transition hover:bg-accent-hover"
		>{backLabel}</a
	>
</main>
