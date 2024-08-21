<script>
	import { Card } from 'flowbite-svelte';
	import waif from '$lib/assets/waif.png';
	import waif2 from '$lib/assets/waif2.png';
	import kc from '$lib/assets/kawancurhat.png'
	import guthib from'$lib/assets/github-mark.svg';

	let imgSrc = waif;	

	// @ts-ignore
	function handleHover(event) {
		imgSrc = event.type === 'mouseenter' ? waif2 : waif;
	}
</script>

<svelte:head>
	<title>Knyghtwebsite</title>
	<meta name="description" content="knyghtw personal website" />
</svelte:head>

<div
	class="flex sticky top-0 pt-5 pb-5 -mb-10 justify-between text-xl bg-gradient-to-b from-black/5 backdrop-blur z-50"
>
	<a class="ml-44 font-bold" href="/#">KNYGHTW</a>
	<div class="flex gap-x-16 mr-44">
		<a href="#about">About</a>
		<a href="#projects">Project</a>
		<a href="#contact">Contact</a>
	</div>
</div>

<div class="mx-44">
	<img
		alt="knyghtw's waifu"
		src={imgSrc}
		on:mouseenter={handleHover}
		on:mouseleave={handleHover}
		class="absolute right-0 mr-48 mt-20 transition brightness-[.25] hover:brightness-100"
	/>	
	<div class="min-h-screen flex flex-col justify-center pb-32">
		<div class="text-8xl font-medium absolute">
			<p>Hello!</p>
			<p>I'm Knyghtw</p>
			<p>Front End Developer</p>
		</div>
	</div>

	<div class="min-h-screen text-4xl flex flex-col justify-center pb-20" id="about">
		<p class="font-bold">About Me</p>
		<p class="mt-9">
			My name is Bagas Satrya Yogatama. I'm an <b>informatics student</b> from the
			<b>University of Muhammadiyah Malang</b>, pursuing a comprehensive learning experience in both
			<b>mobile</b> and <b>web development</b>. My academic journey in informatics has provided me
			with a strong foundation in computer science principles, including programming languages and
			software development methodologies.
			<br /><br />
			I am proficient in programming languages like <b>Java</b>, <b>Python</b>, <b>Kotlin</b>, and
			<b>JavaScript</b>, enabling me to tackle both <b>mobile</b> and <b>web development</b> projects
			with confidence.
		</p>
	</div>

	<div class="min-h-screen flex flex-col justify-center" id="projects">
		<p class="font-bold text-4xl pb-12">Project</p>

		<div class="flex gap-x-4 mt-4 justify-center">
			<Card img={guthib} class="h-fit">
				<h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white">
					PharmAssist
				</h5>
			</Card>
			<Card img={kc} class="mt-16 h-fit">
				<h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white">
					KawanCurhat
				</h5>
			</Card>
			<Card img={guthib} class="mt-32">
				<h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white">
					Misteri Prasasti
				</h5>
			</Card>
		</div>
	</div>

	<div class="min-h-screen flex flex-col justify-center" id="contact">
		<p class="font-bold text-9xl">Interested?</p>
		<p class="text-4xl font-normal">
			Contact me at: <a href="mailto:tmbwpva@protonmail.com" class="font-medium"
				>tmbwpva@protonmail.com</a
			>
		</p>
		<p class="mt-20 mb-6 text-4xl font-bold">More Links:</p>
		<div class="flex flex-col text-4xl gap-y-6">
			<a href="https://github.com/knyghtw">Github</a>
			<a href="https://www.linkedin.com/in/bagas-satrya-yogatama-500ba5235/">Linkedin</a>
			<a href="https://www.instagram.com/bagas.satryaa/">Instagram</a>
		</div>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: #171717;
		color: white;
		font-family: 'Inter Variable', sans-serif;
		scroll-behavior: smooth;
	}
</style>
