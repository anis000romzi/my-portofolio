<script lang="ts">
	import Button from './ui/button/button.svelte';
	import Input from './ui/input/input.svelte';
	import Label from './ui/label/label.svelte';
	import Textarea from './ui/textarea/textarea.svelte';
</script>

<div
	id="contact"
	class="flex w-full flex-col justify-center gap-10 px-6 py-12 [box-shadow:0_0.3px_0_0_#737373] md:flex-row md:gap-16 md:px-20 md:py-12 lg:gap-24 lg:px-36 lg:py-36"
>
	<p class="shrink-0 font-mono text-xs tracking-widest text-[#CC2A2A] md:text-sm">03 — CONTACT</p>

	<div class="flex w-full flex-col gap-10 md:max-w-xl lg:max-w-2xl">
		<p class="text-lg text-[#EEEEEE] md:text-xl">
			Have a project in mind? Let's build something together!
		</p>
		<form class="flex flex-col gap-6">
			<div class="flex flex-col gap-1.5">
				<Label for="name" class="font-mono text-xs tracking-widest text-[#737373]">NAME</Label>
				<Input id="name" type="text" autocomplete="off" name="contact-fullname" />
			</div>

			<div class="flex flex-col gap-1.5">
				<Label for="email" class="font-mono text-xs tracking-widest text-[#737373]">EMAIL</Label>
				<Input id="email" type="email" autocomplete="off" name="contact-email" />
			</div>

			<div class="flex flex-col gap-1.5">
				<Label for="message" class="font-mono text-xs tracking-widest text-[#737373]">MESSAGE</Label
				>
				<Textarea id="message" />
			</div>

			<Button
				class="mt-5 w-6/12 cursor-pointer border-[#CC2A2A] bg-[#080808] p-5 font-mono tracking-widest text-[#CC2A2A] hover:bg-[#CC2A2A] hover:text-[#080808]"
				>SEND MESSAGE</Button
			>
		</form>
	</div>
</div>
