<script>
	import { Card, Modal, Button } from 'flowbite-svelte';
	import { GithubSolid, ArrowUpOutline } from 'flowbite-svelte-icons';
	import { base } from '$app/paths';	
	import waif from '$lib/assets/waif.png';
	import waif2 from '$lib/assets/waif2.png';
	import kc from '$lib/assets/kawancurhat.png';
	import guthib from '$lib/assets/github-mark.svg';

	let imgSrc = waif;
	let showModal1 = false;
	let showModal2 = false;
	let showModal3 = false;
	const projectData = [
		[
			'PharmAssist',
			'PharmAssist adalah aplikasi manajemen apotek yang dapat membantu apoteker mengelola stok obat, penjualan, dan laporan dengan mudah dan efisien.',
			'Aplikasi ini dirancang menggunakan bahasa C# dan .NET Framework.',
			'https://github.com/knyghtw/PharmAssist',
			guthib
		],
		[
			'KawanCurhat',
			'Our goal is to develop a mental health app to help tackle the global problem of mental health issues.',
			'Recent trends in Indonesia, such as the rising rates of student suicides, highlight the importance of providing individuals with the tools and knowledge they need to lead healthier lives.',
			'https://github.com/KawanCurhat',
			kc
		],
		[
			'Misteri Prasasti',
			'A minisweeper inspired game',
			'Made with Flutter Flame',
			'https://github.com/knyghtw/MisteriPrasasti',
			guthib
		]
	];

	// @ts-ignore
	function handleHover(event) {
		imgSrc = event.type === 'mouseenter' ? waif2 : waif;
	}
</script>

<svelte:head>
	<title>Knyghtwebsite</title>
	<meta name="description" content="knyghtw personal website" />
</svelte:head>

<Modal title={projectData[0][0]} bind:open={showModal1} autoclose outsideclose>
	<p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
		{projectData[0][1]}
	</p>
	<p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
		{projectData[0][2]}
	</p>
	<svelte:fragment slot="footer">
		<Button color="dark" href={projectData[0][3]}
			><GithubSolid class="w-5 h-5 me-2" />View Repository</Button
		>
	</svelte:fragment>
</Modal>

<Modal title={projectData[1][0]} bind:open={showModal2} autoclose outsideclose>
	<p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
		{projectData[1][1]}
	</p>
	<p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
		{projectData[1][2]}
	</p>
	<svelte:fragment slot="footer">
		<Button color="dark" href={projectData[1][3]}
			><GithubSolid class="w-5 h-5 me-2" />View Repository</Button
		>
	</svelte:fragment>
</Modal>

<Modal title={projectData[2][0]} bind:open={showModal3} autoclose outsideclose>
	<p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
		{projectData[2][1]}
	</p>
	<p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
		{projectData[2][2]}
	</p>
	<svelte:fragment slot="footer">
		<Button color="dark" href={projectData[2][3]}
			><GithubSolid class="w-5 h-5 me-2" />View Repository</Button
		>
	</svelte:fragment>
</Modal>

<div
	class="flex sticky top-0 pt-5 pb-5 -mb-10 justify-between text-xl bg-gradient-to-b from-black/5 backdrop-blur z-50"
>
	<a class="ml-44 font-bold" href="{base}/">KNYGHTW</a>
	<div class="flex gap-x-16 mr-44">
		<a href="{base}/#about">About</a>
		<a href="{base}/#projects">Project</a>
		<a href="{base}/#contact">Contact</a>
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
			<p class="transition duration-300 hover:font-bold w-fit">Hello!</p>
			<p class="transition duration-300 hover:font-bold w-fit">I'm Knyghtw</p>
			<p class="transition duration-300 hover:font-bold w-fit">Front End Developer</p>
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
			<Card
				img={projectData[0][4]}
				class="h-fit hover:cursor-pointer"
				on:click={() => (showModal1 = true)}
			>
				<h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white">
					{projectData[0][0]}
				</h5>
			</Card>
			<Card
				img={projectData[1][4]}
				class="mt-16 h-fit hover:cursor-pointer"
				on:click={() => (showModal2 = true)}
			>
				<h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white">
					{projectData[1][0]}
				</h5>
			</Card>
			<Card
				img={projectData[2][4]}
				class="mt-32 h-fit hover:cursor-pointer"
				on:click={() => (showModal3 = true)}
			>
				<h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white">
					{projectData[2][0]}
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
<div class="relative w-full h-full">
	<Button class="!p-2 rounded-full absolute right-6 bottom-4" color="dark" href="/"
		><ArrowUpOutline class="w-10 h-10" /></Button
	>
</div>

<style lang="postcss">
	:global(html) {
		background-color: #171717;
		color: white;
		font-family: 'Inter Variable', sans-serif;
		scroll-behavior: smooth;
	}
</style>
