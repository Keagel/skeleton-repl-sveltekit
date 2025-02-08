<script lang="ts">
	import { Modal } from '@skeletonlabs/skeleton-svelte';

	import IconMenu from '~icons/lucide/menu';
	import IconX from '~icons/lucide/x';

	let drawerState = $state(false);

	const drawerOpen = () => {
		drawerState = true;
	};
</script>

<Modal
	bind:open={drawerState}
	contentBase="preset-filled-surface-50-950 flex flex-col shadow-xl w-[480px]"
	positionerJustify="justify-start"
	positionerAlign=""
	positionerPadding=""
	transitionsPositionerIn={{ x: -480, duration: 200 }}
	transitionsPositionerOut={{ x: -480, duration: 200 }}
	triggerClasses="flex"
>
	{#snippet trigger()}
		<button onclick={drawerOpen} aria-label="Menu">
			<IconMenu class="size-6" />
		</button>
	{/snippet}
	{#snippet content()}
		<div class="flex items-center justify-between p-4 px-8">
			Test
		</div>
	{/snippet}
</Modal>
