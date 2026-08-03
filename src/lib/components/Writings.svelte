<script lang="ts">
	const categories: string[] = ['Essay', 'Engineering', 'Personal'];
	const writings: { title: string; summary: string; category: string; created_at: string }[] = [];
</script>

<div
	id="writings"
	class="flex w-full flex-col justify-center gap-10 px-6 py-12 [box-shadow:0_0.3px_0_0_#737373] md:flex-row md:gap-16 md:px-20 md:py-12 lg:gap-24 lg:px-36 lg:py-36"
>
	<p class="shrink-0 font-mono text-xs tracking-widest text-[#CC2A2A] md:text-sm">02 — WRITINGS</p>

	<div class="flex w-full flex-col gap-7 md:max-w-xl lg:max-w-2xl">
		<p class="text-lg text-[#737373]">
			Occasional essays on software craft, systems thinking, and life adjacent to screens.
		</p>
		<div class="flex gap-3">
			{#each categories as category (category)}
				<div class="p-1 px-3 font-mono text-sm text-[#737373] [box-shadow:0_0_0_0.3px_#737373]">
					<span>{category}</span>
				</div>
			{/each}
		</div>
	</div>

	<!-- Writings List -->
	<div>
		{#each writings as writing (writing.title)}

		{/each}
	</div>
</div>
