<script lang="ts">
	import { page } from '$app/stores'

	const links = [
		['/about', 'About'],
		['/contact', 'Contact']
	]
</script>

<template lang="pug">

	nav
		ul
			+each('links as [path, title], i (title)')

				li(class:active='{$page.path === path}')

					a(
						sveltekit:prefetch
						href='{path}'
					) {title}

</template>

<style>
	nav {
		display: flex;
		justify-content: center;

		padding: 2rem;
	}

	ul {
		display: flex;
		gap: 2rem;

		z-index: 1;
	}

	li {
		list-style: none;
	}

	nav a {
		display: flex;
		align-items: center;

		height: 100%;

		font-size: 1.2rem;
		font-weight: 700;

		text-transform: uppercase;
		text-decoration: none;
		letter-spacing: 10%;

		color: var(--dark-a);

		transition: color 0.15s linear;
	}

	a:hover {
		color: var(--brand-a);
	}
</style>
