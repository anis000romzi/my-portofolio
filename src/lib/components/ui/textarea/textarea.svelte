<script lang="ts">
	import { cn, type WithElementRef, type WithoutChildren } from '$lib/utils.js';
	import type { HTMLTextareaAttributes } from 'svelte/elements';

	let {
		ref = $bindable(null),
		value = $bindable(),
		class: className,
		'data-slot': dataSlot = 'textarea',
		...restProps
	}: WithoutChildren<WithElementRef<HTMLTextareaAttributes>> = $props();
</script>

<textarea
	bind:this={ref}
	data-slot={dataSlot}
	class={cn(
		'flex field-sizing-content min-h-24 w-full appearance-none rounded-none border-0 border-b border-input bg-transparent px-0 py-3 text-sm transition-colors outline-none placeholder:text-muted-foreground focus-visible:border-b-[#CC2A2A] disabled:cursor-not-allowed disabled:bg-input/50 disabled:opacity-50 aria-invalid:border-b-destructive md:text-base dark:bg-input/30 dark:disabled:bg-input/80 dark:aria-invalid:border-b-destructive/50',
		className
	)}
	bind:value
	{...restProps}></textarea>

<style>
	textarea {
		outline: none !important;
		box-shadow: none !important;
		-webkit-tap-highlight-color: transparent;
	}
	textarea:focus,
	textarea:focus-visible {
		outline: none !important;
		box-shadow: none !important;
		border-bottom-color: #cc2a2a !important;
	}
</style>
