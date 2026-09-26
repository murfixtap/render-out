<script lang="ts">
	import { Button } from 'bits-ui';
	import { Zap, ShieldCheck } from '@lucide/svelte';

	const outputFormats = [
		{ id: 1, format: 'svg', text: 'Vector SVG' },
		{ id: 2, format: 'pdf', text: 'Print PDF (CMYK)' },
		{ id: 3, format: 'png', text: 'Lossless PNG' },
		{ id: 4, format: 'mp4', text: 'Video MP4' },
		{ id: 5, format: 'webp', text: 'WebP Package' }
	];

	let selectedIds = $state([1]);
</script>

<section class="grid grid-cols-1 items-center gap-16 py-24 lg:grid-cols-2 lg:gap-20">
	<div class="items flex flex-col gap-16">
		<div class="flex max-w-3xl flex-col gap-5">
			<span class="w-fit rounded-full bg-bg-alt px-3 py-1.5 text-xs font-bold text-accent">
				V3 Engine Now Live
			</span>
			<h1 class="font-outfit text-6xl leading-tight font-extrabold text-heading lg:text-7xl">
				Output perfection. In any format.
			</h1>
			<p class="text-lg sm:max-w-2xl">
				Deploy a premium, high-fidelity asset rendering pipeline. Generate print-ready PDFs,
				production-grade SVGs, ultra-res PNGs, and professional MP4 frames in milliseconds.
			</p>
		</div>

		<div class="flex flex-col gap-4 sm:flex-row">
			<a
				href="#pricing"
				class="w-full rounded-lg bg-accent px-6 py-3.5 text-center font-semibold text-card-bg shadow-[0px_4px_12px_var(--color-accent-shadow)] transition hover:bg-accent-hover sm:w-fit"
				>Start Exporting Free</a
			>
			<a
				href="#contact"
				class="w-full rounded-lg border border-border-main bg-card-bg px-6 py-3.5 text-center font-semibold text-heading transition hover:border-text-muted sm:w-fit"
				>Book API Demo</a
			>
		</div>

		<div class="flex justify-center gap-4 sm:justify-start">
			<span class="flex w-fit items-center gap-2 text-xs font-medium sm:text-sm">
				<Zap class="size-4 text-accent" strokeWidth={2} aria-hidden="true" />
				Sub-80ms rendering
			</span>
			<span class="flex w-fit items-center gap-2 text-xs font-medium sm:text-sm">
				<ShieldCheck class="size-4 text-accent" strokeWidth={2} aria-hidden="true" />
				CMYK & ICC preserved
			</span>
		</div>
	</div>

	<div
		class="flex h-fit flex-col gap-6 rounded-3xl border border-border-main bg-card-bg p-8 shadow-[0px_16px_32px_var(--color-card-shadow)] sm:p-10 lg:p-12"
		aria-labelledby="export-profile-title"
	>
		<div class="flex items-start justify-between gap-4">
			<div class="flex min-w-0 flex-col gap-1">
				<h2 id="export-profile-title" class="truncate font-outfit font-semibold text-heading">
					export_profile_final_v2
				</h2>
				<p class="text-xs text-text-muted">Canvas size: 3840 × 2160 (16:9)</p>
			</div>
			<span class="shrink-0 rounded-md bg-bg-alt px-2 py-1 text-xs font-semibold">4K UHD</span>
		</div>

		<div class="flex flex-col gap-3">
			<p id="formats-label" class="text-sm font-semibold">Select Output Formats</p>
			<div
				class="grid grid-cols-1 gap-2 md:grid-cols-3 lg:flex lg:flex-wrap"
				role="group"
				aria-labelledby="formats-label"
			>
				{#each outputFormats as fmt (fmt.id)}
					{@const active = selectedIds.includes(fmt.id)}
					<Button.Root
						type="button"
						aria-pressed={active}
						class="cursor-pointer rounded-lg border px-3 py-2 text-xs font-semibold transition hover:border-text-muted
							{active ? 'border-accent bg-bg-alt text-accent' : 'border-border-main bg-bg-primary'}"
						onclick={() => {
							selectedIds = active
								? selectedIds.filter((id) => id !== fmt.id)
								: [...selectedIds, fmt.id];
						}}
					>
						{fmt.text}
					</Button.Root>
				{/each}
			</div>
		</div>

		<div class="flex flex-col gap-3">
			<div class="flex items-center justify-between gap-4">
				<p class="text-xs font-medium">Processing optimization layers</p>
				<p class="text-xs font-bold text-accent">Ready</p>
			</div>
			<div
				role="progressbar"
				aria-label="Processing optimization layers"
				aria-valuemin="0"
				aria-valuemax="100"
				aria-valuenow="100"
				class="h-1.5 rounded-full bg-border-main"
			>
				<span class="block h-full w-full rounded-full bg-accent"></span>
			</div>
		</div>

		<Button.Root
			type="button"
			class="w-full rounded-[10px] bg-accent p-3.5 text-xs font-bold text-card-bg transition hover:bg-accent-hover"
			>Process and Generate Package (4.2 MB)</Button.Root
		>
	</div>
</section>
