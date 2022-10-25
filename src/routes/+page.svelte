<script lang="ts">
	import type { PageData } from './$types';

	export let data: PageData;
	$: ({ tutorials } = data);

	data.tutorials.forEach((item:any) => {
		console.log('>>>> ' + item.title)
	});

</script>

<svelte:head>
	<title>Sample App</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<div class="wrapper">
		{#each tutorials as tutorial}
				<input hidden name="id" type="text" value={tutorial._id} />
				<input hidden name="title" type="text" value={tutorial.title} />
				<input hidden name="state" type="number" value={tutorial.state} />
				<button
					class="button +
					 {tutorial.state == 0 ? 'button--default' : ''} +
					  {tutorial.state == 1 ? 'button--process' : ''} +
					   {tutorial.state == 2 ? 'button--success' : ''} "
				>
					<div class="button__icon-wrapper">
						<div class="button__icon" />
					</div>
					<div class="button__text-wrapper" style="width: {tutorial.length}em">
						<div class="button__text button__text--default">{tutorial.title}</div>
						<div class="button__text button__text--process">{tutorial.title}</div>
						<div class="button__text button__text--success">{tutorial.title}</div>
					</div>
				</button>
		{/each}
	</div>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
