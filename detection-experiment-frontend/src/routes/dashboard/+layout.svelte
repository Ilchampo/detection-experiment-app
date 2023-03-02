<script lang="ts">
	import { AppShell } from '@skeletonlabs/skeleton';
	import { page } from '$app/stores';
	import { fade } from 'svelte/transition';

	import AppRail from '$lib/components/global/AppRail.svelte';
	import Footer from '$lib/components/global/Footer.svelte';
	import Header from '$lib/components/global/Header.svelte';
</script>

<AppShell>
	<svelte:fragment slot="header"><Header /></svelte:fragment>
	<svelte:fragment slot="sidebarLeft"><AppRail /></svelte:fragment>
	<!-- Router Slot -->
	{#key $page}
		<div class="h-full p-4" in:fade={{ delay: 300 }}><slot /></div>
	{/key}
	<!-- ---- / ---- -->
	<svelte:fragment slot="pageFooter"><Footer /></svelte:fragment>
</AppShell>
