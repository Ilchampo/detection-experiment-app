<script lang="ts">
	import { AppBar } from '@skeletonlabs/skeleton';
	import { page } from '$app/stores';

	import SvgIcons from '$lib/components/SvgIcons/SvgIcons.svelte';

	$: title = $page.url.pathname.split('/').slice(-1);
</script>

<svelte:head><title>Detection Experiment | {title}</title></svelte:head>

<AppBar>
	<svelte:fragment slot="lead">
		<h3>
			<span class="gradient-heading"
				>Detection Experiment | <span class="capitalize">{title}</span></span
			>
		</h3>
	</svelte:fragment>

	<svelte:fragment slot="trail">
		<a href="/">
			<button class="btn-icon variant-filled-primary"
				><span>
					<SvgIcons name="play" title="play" height="h-4" width="w-4" />
				</span></button
			></a
		>
	</svelte:fragment>
</AppBar>
