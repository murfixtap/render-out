<script lang="ts">
	import { Layers, Frame, Box, CreditCard, Database, Wrench } from '@lucide/svelte';

	const trustedBy = [
		{ id: 1, name: 'Linear', Icon: Layers },
		{ id: 2, name: 'Figma', Icon: Frame },
		{ id: 3, name: 'Vercel', Icon: Box },
		{ id: 4, name: 'Stripe', Icon: CreditCard },
		{ id: 5, name: 'Supabase', Icon: Database },
		{ id: 6, name: 'Retool', Icon: Wrench }
	];
</script>

<section class="border-t border-b border-border-main py-12" aria-label="Trusted by">
	<p class="text-center text-xs font-semibold text-text-muted">
		Trusted by infrastructure and design leaders globally
	</p>

	<div class="marquee mt-10">
		<div class="marquee__track">
			{#each Array(6) as _, i (i)}
				<ul class="marquee__group" aria-hidden={i > 0 ? 'true' : undefined}>
					{#each trustedBy as leader (leader.id)}
						{@const Icon = leader.Icon}
						<li class="flex gap-2 text-sm font-semibold text-text-muted">
							<Icon size="20px" aria-hidden="true" />{leader.name}
						</li>
					{/each}
				</ul>
			{/each}
		</div>
	</div>
</section>

<style>
	.marquee {
		overflow: hidden;
		mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
		-webkit-mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
	}

	.marquee__track {
		display: flex;
		width: max-content;
		animation: marquee-left 60s linear infinite;
	}

	.marquee__group {
		display: flex;
		align-items: center;
		gap: 4rem;
		padding-right: 4rem;
		flex-shrink: 0;
	}

	@keyframes marquee-left {
		from {
			transform: translateX(0);
		}
		to {
			transform: translateX(-50%);
		}
	}

	@media (prefers-reduced-motion: reduce) {
		.marquee__track {
			animation: none;
		}

		.marquee__group[aria-hidden='true'] {
			display: none;
		}
	}
</style>
