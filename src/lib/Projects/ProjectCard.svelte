<script>
	import ImageLoader from '$lib/ImageLoader.svelte';
	import clsx from 'clsx';
	import { TwitterLogo, Globe } from 'phosphor-svelte';

	export let name;
	export let tagline;
	export let projectLink;
	export let twitterLink;
	export let imgUrl;
</script>

<div
	class={clsx(
		'project-card relative h-[331px] w-[304px] rounded-xl flex flex-col justify-between p-8',
		$$props.class
	)}
>
	<div class="flex flex-col">
		<div class="flex flex-col items-start gap-4">
			<ImageLoader
				src={imgUrl}
				height={32}
				width="auto"
				alt=""
				class="rounded-full h-[32px] w-auto"
				loading="lazy"
			/>
			<h2 class="font-secondary text-[24px] font-bold text-white">{name}</h2>
		</div>
		<p class="text-white font-primary font-medium">
			{tagline}
		</p>
	</div>
	<div class="flex gap-4">
		<a href={projectLink} target="_blank">
			<Globe size={24} color="white" />
		</a>
		<a href={twitterLink} target="_blank">
			<TwitterLogo size={24} color="white" />
		</a>
	</div>
</div>

<style>
	.project-card {
		background: linear-gradient(180deg, #000000 -18.75%, rgba(0, 0, 0, 0) 114.5%),
			linear-gradient(180deg, #1d1d1d 0%, rgba(22, 22, 22, 0) 100%);
		border: 1px solid #3f3f3f;
		transition: background 0.5s, border 0.5s ease-in-out;
	}
	.project-card:hover {
		content: '';
		width: 304px;
		height: 331px;
		background: linear-gradient(180deg, #232323 -18.75%, #121212 25.65%);
		border: 1px solid #f6f3f3;
		opacity: 1;
	}
</style>
