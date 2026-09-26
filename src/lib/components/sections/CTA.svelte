<script lang="ts">
	import { resolve } from '$app/paths';
</script>

<section
	id="contact"
	class="flex flex-col items-center gap-8 rounded-4xl bg-heading px-8 py-12 text-center sm:px-10 lg:px-16"
>
	<div class="flex max-w-3xl flex-col gap-4">
		<h2 class="font-outfit text-5xl leading-tight font-extrabold text-card-bg">
			Ready to deploy professional exports?
		</h2>
		<p class="text-text-alt">
			Join over 10,000 developers and agencies who rely on render.out for sub-millisecond document,
			design, and media conversion pipelines.
		</p>
	</div>

	<div class="flex w-full flex-col gap-4 sm:w-fit sm:flex-row">
		<a
			href="#pricing"
			class="rounded-lg bg-accent px-6 py-3.5 font-semibold text-card-bg transition hover:bg-accent-hover"
			>Get Started Free</a
		>
		<a
			href={resolve('/contact')}
			class="rounded-lg px-6 py-3.5 font-semibold text-card-bg ring-1 ring-card-bg transition hover:ring-text-muted"
			>Contact Sales</a
		>
	</div>
</section>
