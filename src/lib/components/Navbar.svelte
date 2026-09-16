<script lang="ts">
	import { resolve } from '$app/paths';

	let mobileMenuOpen = $state(false);
	let navEl: HTMLElement | undefined = $state();
	let navHeight = $state(0);

	const links = [
		{ id: 'about', href: '#about', label: 'ABOUT' },
		{ id: 'projects', href: '#projects', label: 'PROJECTS' },
		{ id: 'writings', href: '#writings', label: 'WRITINGS' },
		{ id: 'contact', href: '#contact', label: 'CONTACT' }
	];

	function closeMenu() {
		mobileMenuOpen = false;
	}

	$effect(() => {
		if (!navEl) return;
		const update = () => (navHeight = navEl!.offsetHeight);
		update();
		const ro = new ResizeObserver(update);
		ro.observe(navEl);
		return () => ro.disconnect();
	});
</script>

<nav
	bind:this={navEl}
	class="section-x sticky top-0 z-50 bg-[#080808]/50 py-5 font-mono text-[#EEEEEE] [box-shadow:0_0.3px_0_0_#737373] backdrop-blur-md md:py-6"
>
	<div class="flex items-center justify-between">
		<a href={resolve('/')}><span class="font-bold">anis00<span class="text-[#CC2A2A]">0romzi.</span></span></a>

		<ul class="hidden list-none gap-10 text-xs font-light tracking-widest text-[#737373] md:flex">
			{#each links as link (link.id)}
				<!-- eslint-disable-next-line svelte/no-navigation-without-resolve -->
				<li class="hover:text-[#CC2A2A]"><a href={link.href}>{link.label}</a></li>
			{/each}
		</ul>

		<button
			class="flex flex-col gap-1.5 md:hidden"
			aria-label="Toggle menu"
			aria-expanded={mobileMenuOpen}
			onclick={() => (mobileMenuOpen = !mobileMenuOpen)}
		>
			<span
				class="h-0.5 w-6 bg-[#EEEEEE] transition-transform duration-200 {mobileMenuOpen
					? 'translate-y-2 rotate-45'
					: ''}"
			></span>
			<span
				class="h-0.5 w-6 bg-[#EEEEEE] transition-opacity duration-200 {mobileMenuOpen
					? 'opacity-0'
					: ''}"
			></span>
			<span
				class="h-0.5 w-6 bg-[#EEEEEE] transition-transform duration-200 {mobileMenuOpen
					? '-translate-y-2 -rotate-45'
					: ''}"
			></span>
		</button>
	</div>
</nav>

{#if mobileMenuOpen}
	<button
		class="fixed inset-0 z-40 cursor-default bg-transparent md:hidden"
		aria-label="Close menu"
		onclick={closeMenu}
	></button>

	<ul
		class="section-x font-mono fixed inset-x-0 z-50 flex list-none flex-col gap-5 bg-[#080808]/50 py-5 font-light text-[#737373] [box-shadow:0_0.3px_0_0_#737373] backdrop-blur-md md:hidden"
		style="top: {navHeight}px"
	>
		{#each links as link (link.id)}
			<li class="hover:text-[#CC2A2A]">
				<!-- eslint-disable-next-line svelte/no-navigation-without-resolve -->
				<a href={link.href} onclick={closeMenu}>{link.label}</a>
			</li>
		{/each}
	</ul>
{/if}
