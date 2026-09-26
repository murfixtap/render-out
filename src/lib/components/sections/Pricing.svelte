<script lang="ts">
	import { Check } from '@lucide/svelte';

	const plans = [
		{
			id: 'standard',
			name: 'Standard',
			description: 'Perfect for individual designers and developers creating simple assets.',
			price: '$0',
			period: '/ forever',
			features: [
				'PDF and high-res PNG outputs',
				'Up to 50 exports per month',
				'Resolution limited to 150 DPI',
				'Standard processing queues',
				'Community support'
			],
			cta: 'Get Started Free',
			highlighted: false
		},
		{
			id: 'pro',
			name: 'Professional',
			badge: 'Most Popular',
			description: 'High-fidelity pipeline with lossless vector rendering and batch processing.',
			price: '$29',
			period: '/ month',
			features: [
				'Lossless Vector SVG & PDF exports',
				'Print-ready CMYK + ICC profile embed',
				'Unlimited batch generation',
				'Ultra-high resolution (600 DPI)',
				'Zero watermark on outputs',
				'Priority render pipelines'
			],
			cta: 'Upgrade to Pro',
			highlighted: true
		},
		{
			id: 'enterprise',
			name: 'Enterprise',
			description: 'Custom format engines, dedicated infrastructure, and secure API solutions.',
			price: 'Custom',
			period: null,
			features: [
				'Native video MP4/ProRes rendering',
				'Dedicated rendering instance',
				'Unlimited REST API access keys',
				'SLA guaranteed uptime (99.99%)',
				'Dedicated developer support',
				'Custom contracts & invoices'
			],
			cta: 'Contact Sales',
			highlighted: false
		}
	];
</script>

<section id="pricing" class="flex flex-col gap-12 py-24">
	<div class="mx-auto flex max-w-3xl flex-col gap-4 text-center">
		<span class="text-sm font-bold text-accent">Predictable Plans</span>
		<h2 class="font-outfit text-4xl leading-tight font-extrabold text-heading">
			Flexible tiers built for creators and platforms
		</h2>
		<p>Start free, upgrade as your pipeline demands. Save 20% on annual billing.</p>
	</div>

	<div class="grid gap-6 md:grid-cols-2 xl:grid-cols-3">
		{#each plans as plan (plan.id)}
			<article
				class="flex h-full flex-col gap-8 rounded-3xl bg-card-bg p-10 ring-1
					{plan.highlighted ? 'border-accent ring-2 ring-accent' : 'ring-border-main'}"
			>
				<div class="flex flex-col gap-4">
					<div class="flex flex-col-reverse gap-6 min-[400px]:flex-row min-[400px]:items-center">
						<h3 class="font-outfit text-2xl font-bold text-heading">{plan.name}</h3>
						{#if plan.badge}
							<span
								class="flex h-fit w-fit items-center rounded-full bg-accent px-2.5 py-1 text-center text-xs font-bold text-card-bg"
							>
								{plan.badge}
							</span>
						{/if}
					</div>

					<p class="text-sm">
						{plan.description}
					</p>

					<div class="flex items-baseline gap-1">
						<p class="font-outfit text-4xl font-extrabold text-heading">{plan.price}</p>
						<p class="h-fit text-sm text-text-primary">{plan.period}</p>
					</div>
				</div>

				<hr class="h-px border-0 bg-border-main" />

				<ul class="flex flex-col gap-4">
					{#each plan.features as feature (feature)}
						<li class="flex items-center gap-3 text-sm text-heading">
							<span class="flex size-6 shrink-0 items-center justify-center rounded-full bg-bg-alt">
								<Check class="text-accent" stroke-width="5" size="14" aria-hidden="true" />
							</span>
							{feature}
						</li>
					{/each}
				</ul>

				<a
					href="#contact"
					class="mt-auto w-full rounded-lg px-6 py-3.5 text-center font-semibold transition
						{plan.highlighted
						? 'bg-accent text-card-bg hover:bg-accent-hover'
						: 'bg-card-bg text-heading ring-1 ring-border-main hover:ring-text-muted'}"
					>{plan.cta}</a
				>
			</article>
		{/each}
	</div>
</section>
