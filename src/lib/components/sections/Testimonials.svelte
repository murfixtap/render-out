<script lang="ts">
	import alinaImg from '$lib/assets/images/Alina.webp';
	import marcusImg from '$lib/assets/images/Marcus.webp';

	const testimonials = [
		{
			id: 1,
			name: 'Marcus Vance',
			jobTitles: 'VP Engineering, Figma plugins',
			description:
				'We migrated our asset generation microservices to render.out. It reduced our server compute bills by 40% and cut conversion failures down to literally zero.',
			avatar: marcusImg
		},
		{
			id: 2,
			name: 'Alina Khasanova',
			jobTitles: 'Lead Designer, Retool',
			description:
				'Outstanding resolution consistency. Generating print-ready CMYK PDFs for catalog workflows was always a nightmare, but this engine does it in 50 milliseconds.',
			avatar: alinaImg
		}
	];
</script>

<section class="flex flex-col gap-12 py-24">
	<div class="mx-auto flex max-w-3xl flex-col gap-4 text-center">
		<span class="text-sm font-bold text-accent">Testimonials</span>
		<h2 class="font-outfit text-3xl leading-tight font-extrabold text-heading lg:text-4xl">
			What engineering leaders are saying
		</h2>
	</div>

	<ul class="grid grid-cols-1 gap-6 md:grid-cols-2">
		{#each testimonials as review (review.id)}
			<li class="flex h-full flex-col gap-6 rounded-2xl bg-card-bg p-8 ring-1 ring-border-main">
				<p>"{review.description}"</p>
				<div class="flex items-center gap-3">
					<img
						src={review.avatar}
						class="size-10 rounded-full"
						alt=""
						loading="lazy"
						decoding="async"
					/>
					<div>
						<h3 class="text-sm font-semibold text-heading">{review.name}</h3>
						<p class="text-xs text-text-muted">{review.jobTitles}</p>
					</div>
				</div>
			</li>
		{/each}
	</ul>
</section>
