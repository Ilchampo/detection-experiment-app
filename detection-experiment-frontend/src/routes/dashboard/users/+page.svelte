<script lang="ts">
	import type { PageData } from './$types';

	import DataTable from '$lib/components/global/DataTable.svelte';
	const sourceData = [
		{ id: 1, name: 'Juan' },
		{ id: 2, name: 'Pablo' }
	];
	const columns = ['id', 'name'];

	export let data: PageData;
</script>

<div class="card variant-glass h-full">
	<div class="card-header">
		<h2>Users Panel</h2>
	</div>

    <DataTable columns={columns} sourceData={sourceData}/>

	<div class="card-footer" />
</div>
