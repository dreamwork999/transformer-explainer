<script>
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';
	import InputForm from '~/components/InputForm.svelte';
	import { ga } from '~/utils/event';

	export let isActive;
</script>

<div class="top-bar flex w-full items-center gap-4 px-10 py-2 pb-3" class:active={isActive}>
	<div class="logo text-bold text-gray-700">
		<!-- T<span class="small">RANSFORMER</span> E<span class="small">XPLAINER</span> -->
		<img src="./logo.png" alt="Transformer Explainer Logo" class="h-8" />
	</div>
	<div class="inputs flex grow items-center">
		<div class="input-wrapper w-full" class:active={isActive}>
			<InputForm />
		</div>
	</div>
	
</div>

<style lang="scss">
	.top-bar {
		background: linear-gradient(to bottom, rgb(17, 24, 39) 60%, rgba(255, 255, 255, 0) 100%);
		.input-wrapper {
			&.active {
				opacity: 1;
				pointer-events: initial;
			}
			opacity: 0;
			transition: opacity 0.2s;
			pointer-events: none;
		}
		.logo {
			flex-shrink: 0;
			white-space: nowrap;
			font-family: 'Jersey 10', sans-serif;

			font-optical-sizing: auto;
			font-style: normal;

			font-size: 2rem;
			// color: theme('colors.blue.800');

			background: linear-gradient(
				to right,
				theme('colors.blue.500') 0%,
				theme('colors.purple.500') 60%
			);
			-webkit-background-clip: text;
			-webkit-text-fill-color: transparent;

			.small {
				font-size: 1.8rem;
			}
		}
		.icons {
			flex-shrink: 0;
			svg {
				fill: theme('colors.gray.600');
			}
		}
	}
</style>
