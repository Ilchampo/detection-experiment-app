<script lang="ts">
	import type { DataTableModel } from '@skeletonlabs/skeleton';

	import { dataTableHandler, createDataTableStore } from '@skeletonlabs/skeleton';
	import { tableInteraction, tableA11y } from '@skeletonlabs/skeleton';

	export const columns: string[] = [];
	export let sourceData: any;

	const dataTableStore = createDataTableStore(sourceData, {
		search: '',
		sort: '',
		pagination: { offset: 0, limit: 0, size: 0, amounts: [1, 3, 5, 7, 10] }
	});

	dataTableStore.subscribe((model) => {
		dataTableHandler(model);
	});
</script>

{#if !columns || !sourceData}
	<h3>Please provide columns and source data for the data table!</h3>
{:else}
	{#each sourceData as data}
		<p>{data.name}</p>
	{/each}

	{#each columns as column}
		<p>{column}</p>
	{/each}
{/if}
