<script lang="ts">
	import Icon from '@iconify/svelte';
	import Reveal from './Reveal.svelte';

	// https://icon-sets.iconify.design
	const skills: { name: string; icon: string }[] = [
		{ name: 'Node.js', icon: 'devicon:nodejs' },
		{ name: 'PHP', icon: 'material-icon-theme:php-elephant-pink' },
		{ name: 'Express.js', icon: 'skill-icons:expressjs-light' },
		{ name: 'NestJS', icon: 'devicon:nestjs' },
		{ name: 'Laravel', icon: 'devicon:laravel' },
		{ name: 'Codeigniter', icon: 'logos:codeigniter-icon' },
		{ name: 'MySQL', icon: 'devicon:mysql' },
		{ name: 'PostgreSQL', icon: 'devicon:postgresql' },
		{ name: 'MongoDB', icon: 'devicon:mongodb' },
		{ name: 'Redis', icon: 'devicon:redis' },
		{ name: 'HTML', icon: 'vscode-icons:file-type-html' },
		{ name: 'CSS', icon: 'skill-icons:css' },
		{ name: 'JavaScript', icon: 'devicon:javascript' },
		{ name: 'TypeScript', icon: 'devicon:typescript' },
		{ name: 'React.js', icon: 'devicon:react' },
		{ name: 'Vue.js', icon: 'devicon:vuejs' },
		{ name: 'Next.js', icon: 'devicon:nextjs' },
		{ name: 'Nuxt.js', icon: 'devicon:nuxt' },
		{ name: 'Tailwind CSS', icon: 'devicon:tailwindcss' },
		{ name: 'Git', icon: 'devicon:git' },
		{ name: 'Docker', icon: 'devicon:docker' }
	];
</script>

<div
	id="about"
	class="flex w-full flex-col justify-center gap-10 px-6 py-12 [box-shadow:0_0.3px_0_0_#737373] md:flex-row md:gap-16 md:px-20 md:py-12 lg:gap-24 lg:px-36 lg:py-36"
>
	<p class="shrink-0 font-mono text-xs tracking-widest text-[#CC2A2A] md:text-sm">00 — ABOUT</p>

	<div class="flex w-full flex-col gap-10 md:max-w-xl lg:max-w-2xl">
		<p class="text-lg text-[#EEEEEE] md:text-2xl">
			I build software that earns trust through clarity. Eight years working across early-stage
			startups and mid-size product teams — always at the intersection of engineering rigour and
			design sensibility.
		</p>
		<Reveal delay={150}>
			<p class="text-md text-[#737373] md:text-lg">
				Previously at Figma (infrastructure), Linear (API platform), and two companies I co-founded.
				I care deeply about developer experience, performance, and systems that degrade gracefully.
				When I'm not writing code I'm usually reading architecture theory or hiking somewhere
				remote.
			</p>
		</Reveal>
		<Reveal delay={300}>
			<div class="flex flex-col gap-5">
				<p class="font-mono text-sm tracking-widest text-[#CC2A2A]">SKILLS</p>
				<div class="flex flex-wrap gap-2 font-mono text-xs text-[#737373]">
					{#each skills as skill (skill.name)}
						<div
							class="flex items-center justify-center gap-2 p-2 [box-shadow:0_0_0_0.3px_#737373] hover:text-[#CC2A2A] hover:[box-shadow:0_0_0_0.3px_#CC2A2A]"
						>
							<Icon icon={skill.icon} width="13" height="13" />
							<span>{skill.name}</span>
						</div>
					{/each}
				</div>
			</div>
		</Reveal>
	</div>
</div>
