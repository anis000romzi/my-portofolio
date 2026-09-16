<script lang="ts">
	import { resolve } from '$app/paths';
	import Reveal from './Reveal.svelte';

	const projects = [
		{
			title: 'Project testing 1',
			description:
				'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum',
			skills: ['Rust', 'C++', 'JavaScript'],
			year: 2077
		},
		{
			title: 'Project testing 2',
			description:
				'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum',
			skills: ['Haskell', 'Go', 'Ruby'],
			year: 2078
		},
		{
			title: 'Project testing 3',
			description:
				'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum',
			skills: ['Haskell', 'Go', 'Ruby'],
			year: 2078
		},
		{
			title: 'Project testing 4',
			description:
				'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum',
			skills: ['Haskell', 'Go', 'Ruby'],
			year: 2078
		},
		{
			title: 'Project testing 5',
			description:
				'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum',
			skills: ['Haskell', 'Go', 'Ruby'],
			year: 2078
		}
	];
</script>

<div
	id="projects"
	class="section-x section-y flex flex-col gap-16 md:gap-20 [box-shadow:0_0.3px_0_0_#737373]"
>
	<div class="section-gap flex w-full flex-col justify-center md:flex-row">
		<p class="shrink-0 font-mono text-xs tracking-widest text-[#CC2A2A] md:text-sm">
			01 — PROJECTS
		</p>

		<div class="flex w-full flex-col gap-7 md:max-w-xl lg:max-w-2xl">
			<p class="text-lg text-[#737373]">
				A selection of projects shipped in the last two years. Full case studies available on
				request.
			</p>
		</div>
	</div>

	<div class="mb-10 w-full">
		{#each projects as project, i (project.title)}
			<div
				class="[box-shadow:0_-0.3px_0_0_#737373] last:[box-shadow:0_-0.3px_0_0_#737373,0_0.3px_0_0_#737373]"
			>
				<Reveal>
					<a href={resolve('/')}>
						<div
							class="group flex flex-col gap-4 p-5 transition-colors duration-200 hover:bg-[#CC2A2A]/5 sm:p-7 md:flex-row md:items-center md:justify-between md:gap-8 lg:gap-16"
						>
							<div class="flex items-center justify-between md:hidden">
								<span class="font-mono text-sm text-[#363535]"
									>{String(i + 1).padStart(2, '0')}</span
								>
								<span class="font-mono text-xs text-[#737373]">{project.year}</span>
							</div>
							<span class="hidden font-mono text-sm text-[#363535] md:block"
								>{String(i + 1).padStart(2, '0')}</span
							>
							<div class="flex w-full flex-col gap-3 md:w-6/12 md:gap-4">
								<p class="text-xl transition-colors duration-200 group-hover:text-[#CC2A2A]">
									{project.title}
								</p>
								<p class="line-clamp-3 text-sm text-[#737373]">
									{project.description}
								</p>
							</div>
							<div class="flex flex-wrap gap-2">
								{#each project.skills as skill (skill)}
									<div
										class="p-1 px-3 font-mono text-xs text-[#737373] [box-shadow:0_0_0_0.3px_#737373]"
									>
										<span>{skill}</span>
									</div>
								{/each}
							</div>
							<span class="hidden font-mono text-xs text-[#737373] md:block">{project.year}</span>
						</div>
					</a>
				</Reveal>
			</div>
		{/each}
	</div>
</div>
