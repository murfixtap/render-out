<script lang="ts">
	import { Header, Hero, TrustedBy, Pricing, Features, Testimonials, CTA, Footer } from '$lib';
</script>

<Header />

<main id="main-content" class="flex flex-col">
	<section class="mx-auto w-full max-w-7xl px-4 sm:px-6 md:px-8 lg:px-10">
		<Hero />
	</section>

	<TrustedBy />

	<section class="mx-auto w-full max-w-7xl px-4 sm:px-6 md:px-8 lg:px-10">
		<Pricing />
	</section>

	<Features />

	<section class="mx-auto w-full max-w-7xl px-4 sm:px-6 md:px-8 lg:px-10">
		<Testimonials />
		<CTA />
	</section>
</main>

<Footer />
