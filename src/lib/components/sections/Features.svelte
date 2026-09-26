<script lang="ts">
	import { Layers2, ArrowLeftRight, Expand, CircleX, CloudUpload, Palette } from '@lucide/svelte';

	const features = [
		{
			id: 'export',
			name: 'Batch Export',
			description:
				'Transform heavy workspace design data into production-ready assets without dropping layers, clipping vectors, or desaturating colors.',
			Icon: Layers2
		},
		{
			id: 'format',
			name: 'Format Conversion',
			description:
				'Convert between complex design profiles. Output print-ready vector PDFs, SVGs, high-depth WebPs, and raw matrices effortlessly.',
			Icon: ArrowLeftRight
		},
		{
			id: 'resolution',
			name: 'Resolution Control',
			description:
				'Scale canvas dimensions up to 10x without losing detail. Preserves perfect vector coordinates and embeds custom ICC color profiles.',
			Icon: Expand
		},
		{
			id: 'watermark',
			name: 'Watermark Removal',
			description:
				'Embed custom system signatures or strip out all engine indicators entirely for true white-label platform output.',
			Icon: CircleX
		},
		{
			id: 'cloud',
			name: 'Cloud Delivery',
			description:
				'Deliver outputs directly to your cloud stores. Seamless integration with AWS S3, Cloudflare R2, Google Cloud, and private CDNs.',
			Icon: CloudUpload
		},
		{
			id: 'icc',
			name: 'ICC Color Profiles',
			description:
				'Preserve color accuracy from screens to final prints. Automatically bundle sRGB, Display P3, and CMYK color space standards.',
			Icon: Palette
		}
	];
</script>

<section class="w-full bg-card-bg py-24">
	<div class="mx-auto flex w-full max-w-7xl flex-col gap-16 px-4 sm:px-6 md:px-8 lg:px-10">
		<div class="flex max-w-3xl flex-col gap-4">
			<span class="text-sm font-bold text-accent">Engine Capabilities</span>
			<h2 class="font-outfit text-4xl leading-tight font-extrabold text-heading">
				Engineered for modern production pipelines
			</h2>
			<p>
				Transform heavy workspace design data into production-ready assets without dropping layers,
				clipping vectors, or desaturating colors.
			</p>
		</div>
		<ul class="grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3">
			{#each features as feature (feature.id)}
				{@const Icon = feature.Icon}
				<li class="flex flex-col gap-5 rounded-2xl bg-card-bg p-8 ring-1 ring-border-main">
					<div
						class="flex size-12 items-center justify-center rounded-xl bg-bg-alt"
						aria-hidden="true"
					>
						<Icon class="text-accent" size="24px" />
					</div>
					<div class="flex flex-col gap-2">
						<h3 class="font-outfit text-xl font-semibold text-heading">{feature.name}</h3>
						<p class="text-sm">
							{feature.description}
						</p>
					</div>
				</li>
			{/each}
		</ul>
	</div>
</section>
