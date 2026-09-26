<script lang="ts">
	import { resolve } from '$app/paths';
	import Logo from '$lib/components/layout/Logo.svelte';

	const links = [
		{
			id: 'product',
			name: 'Product',
			items: [
				{ label: 'Engine', href: '/engine' },
				{ label: 'Formats', href: '/formats' },
				{ label: 'Pricing', href: '/pricing' },
				{ label: 'CLI & API', href: '/cli-api' }
			]
		},
		{
			id: 'resources',
			name: 'Resources',
			items: [
				{ label: 'Documentation', href: '/docs' },
				{ label: 'API Spec', href: '/api' },
				{ label: 'Guides', href: '/guides' },
				{ label: 'Support', href: '/support' }
			]
		},
		{
			id: 'company',
			name: 'Company',
			items: [
				{ label: 'About Us', href: '/about' },
				{ label: 'Customers', href: '/customers' },
				{ label: 'Careers', href: '/careers' },
				{ label: 'Contact', href: '/contact' }
			]
		}
	] as const;

	const legalLinks = [
		{ label: 'Privacy Policy', href: '/privacy' },
		{ label: 'Terms of Service', href: '/terms' },
		{ label: 'SLA Status', href: '/status' }
	] as const;
</script>

<footer
	class="mx-auto flex w-full max-w-7xl flex-col gap-16 px-4 pt-24 pb-12 sm:px-6 md:px-8 lg:px-10"
>
	<div class="flex flex-col gap-8">
		<div class="flex flex-col gap-4">
			<Logo />
			<p class="text-sm">
				The premium file rendering and format conversion pipeline for professional creators and
				digital platforms.
			</p>
		</div>

		<div class="grid grid-cols-2 gap-8 sm:grid-cols-3">
			{#each links as section (section.id)}
				<div class="flex flex-col gap-4">
					<h2 class="font-outfit text-sm font-bold text-heading uppercase">{section.name}</h2>
					<ul class="flex flex-col gap-4">
						{#each section.items as item (item.href)}
							<li>
								<a href={resolve(item.href)} class="text-sm transition hover:text-heading"
									>{item.label}</a
								>
							</li>
						{/each}
					</ul>
				</div>
			{/each}
		</div>
	</div>

	<hr class="h-px border-0 bg-border-main" />

	<div class="flex flex-col justify-between gap-6 lg:flex-row">
		<p class="text-text-muted">© 2026 render.out Technologies, Inc. All rights reserved.</p>

		<ul class="flex flex-col justify-between gap-4 text-text-muted min-[400px]:flex-row">
			{#each legalLinks as item (item.href)}
				<li>
					<a href={resolve(item.href)} class="transition hover:text-heading">{item.label}</a>
				</li>
			{/each}
		</ul>
	</div>
</footer>
