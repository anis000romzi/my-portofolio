<script lang="ts">
	import Hero from '$lib/components/Hero.svelte';
	import About from '$lib/components/About.svelte';
	import Projects from '$lib/components/Projects.svelte';
	import Writings from '$lib/components/Writings.svelte';
	import Contact from '$lib/components/Contact.svelte';
	import Reveal from '$lib/components/Reveal.svelte';
</script>

<div>
	<Reveal>
		<Hero />
	</Reveal>
	<Reveal>
		<About />
	</Reveal>
	<Reveal>
		<Projects />
	</Reveal>
	<Reveal>
		<Writings />
	</Reveal>
	<Reveal>
		<Contact />
	</Reveal>
</div>
