<script lang="ts">
	import { onMount } from 'svelte';
	import '../app.css';

	let { children } = $props();

	let visible = $state(false);
	onMount(() => {
		setTimeout(() => {
			visible = true;
		}, 700);
	});
</script>

<div class="flex min-h-[100dvh] w-full flex-col items-center justify-center">
	<main class="w-full max-w-screen-sm px-5 sm:px-3">
		{#if visible}
			{@render children()}
		{:else}
			<div class="space-x-1 text-center text-2xl font-bold text-white">
				<span class="animate-pulse animate-duration-700">●</span>
				<span class="animate-pulse animate-delay-100 animate-duration-700">●</span>
				<span class="animate-pulse animate-delay-200 animate-duration-700">●</span>
			</div>
		{/if}
	</main>
</div>
