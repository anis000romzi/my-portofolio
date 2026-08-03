<script lang="ts">
	import { inView } from '$lib/actions/inView';
	import type { Snippet } from 'svelte';

	let {
		children,
		delay = 0,
		duration = 700,
		y = 40,
		class: className = ''
	}: {
		children: Snippet;
		delay?: number;
		duration?: number;
		y?: number;
		class?: string;
	} = $props();

	let visible = $state(false);
</script>

<div
	use:inView={{ onEnter: () => (visible = true) }}
	class="transition-all ease-out will-change-transform {className}"
	style="transition-duration:{duration}ms; transition-delay:{delay}ms; opacity:{visible ? 1 : 0}; transform:translateY({visible ? 0 : y}px);"
>
	{@render children()}
</div>