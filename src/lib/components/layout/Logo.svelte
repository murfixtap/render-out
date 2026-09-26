<script lang="ts">
	import logo from '$lib/assets/logo.svg';
	import { resolve } from '$app/paths';
</script>

<a
	href={resolve('/')}
	class="flex w-fit items-center gap-2 font-outfit text-xl font-bold select-none"
	aria-label="render.out — home"
>
	<img src={logo} alt="" />
	<span class="text-heading">render.out</span>
</a>
