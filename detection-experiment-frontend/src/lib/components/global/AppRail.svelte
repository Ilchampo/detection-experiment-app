<script lang="ts">
	import { AppRail, AppRailTile } from '@skeletonlabs/skeleton';
	import SvgIcons from '$lib/components/SvgIcons/SvgIcons.svelte';
</script>

<AppRail>
	<svelte:fragment slot="lead">
		<AppRailTile tag="a" href="/dashboard"><SvgIcons name="home" title="home" /></AppRailTile>
	</svelte:fragment>

	<AppRailTile tag="a" href="/dashboard/users"><SvgIcons name="user" title="user" /></AppRailTile>
	<AppRailTile tag="a" href="/dashboard/scores"><SvgIcons name="score" title="score" /></AppRailTile>
	<AppRailTile tag="a" href="/dashboard/scenes"><SvgIcons name="scene" title="scene" /></AppRailTile>
	<AppRailTile tag="a" href="/dashboard/backgrounds"
		><SvgIcons name="background" title="background" /></AppRailTile
	>
	<AppRailTile tag="a" href="/dashboard/stimuli"
		><SvgIcons name="stimulus" title="stimulus" /></AppRailTile
	>

	<svelte:fragment slot="trail">
		<AppRailTile tag="a" href="/dashboard/settings"
			><SvgIcons name="settings" title="settings" /></AppRailTile
		>
		<AppRailTile tag="a" href="/auth/signin"><SvgIcons name="logout" title="logout" /></AppRailTile>
	</svelte:fragment>
</AppRail>
