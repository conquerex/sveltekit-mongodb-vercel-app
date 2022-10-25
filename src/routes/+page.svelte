<script lang="ts">
	import { onMount } from 'svelte';

	onMount(() => {
		const button:any = document.querySelector('.button');
		button.addEventListener('click', function () {
			button.classList.remove('button--default');
			button.classList.add('button--process');
			setTimeout(function () {
				button.classList.remove('button--process');
				button.classList.add('button--success');
			}, 2000);
			setTimeout(function () {
				button.classList.remove('button--success');
				button.classList.add('button--default');
			}, 4500);
		});
	});
</script>

<svelte:head>
	<title>Sample App</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<div class="wrapper">
		<button class="button button--default">
			<div class="button__icon-wrapper">
				<div class="button__icon" />
			</div>
			<div class="button__text-wrapper">
				<div class="button__text button__text--default">Send</div>
				<div class="button__text button__text--process">Cancel</div>
				<div class="button__text button__text--success">Sent!</div>
			</div>
		</button>
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
