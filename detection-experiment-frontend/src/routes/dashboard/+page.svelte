<script lang="ts">
	import { Stepper, Step } from '@skeletonlabs/skeleton';

	import SvgIcons from '$lib/components/SvgIcons/SvgIcons.svelte';
	import Loader from '$lib/components/global/Loader.svelte';

	import type { PageData } from './$types';
	export let data: PageData;

	let isLoading = false;
</script>

{#if isLoading}
	<Loader />
{:else}
	<div class="grid grid-cols-2 gap-4">
		<!-- First column -->
		<div class="flex flex-col gap-4">
			<!-- User header -->
			<div class="card variant-glass">
				<div class="card-header">
					<h2>Welcome back, Pablo!</h2>
				</div>
				<hr class="mt-2 mx-4" />
				<div class="card-content">
					<p>
						We are thrilled to see you again. Thank you for using the Detection Experiment platform,
						we look forward to continuing to serve you with the best possible experience as well as
						updating the platform with new awesome features.
					</p>
				</div>
			</div>

			<!-- Application stats -->
			<div class="flex gap-4 justify-between">
				<!-- Users stats -->
				<div class="card !bg-secondary-500 variant-glass p-4 flex-1">
					<div class="flex flex-col justify-center items-center gap-4">
						<SvgIcons name="user" title="users" height="h-32" width="32" />
						<h4>4 Users</h4>
					</div>
				</div>
				<!-- Scenes stats -->
				<div class="card !bg-secondary-600 variant-glass p-4 flex-1">
					<div class="flex flex-col justify-center items-center gap-4">
						<SvgIcons name="scene" title="scenes" height="h-32" width="32" />
						<h4>4 Scenes</h4>
					</div>
				</div>
				<!-- Backgrounds stats -->
				<div class="card !bg-secondary-700 variant-glass p-4 flex-1">
					<div class="flex flex-col justify-center items-center gap-4">
						<SvgIcons name="background" title="backgrounds" height="h-32" width="32" />
						<h4>4 Backgrounds</h4>
					</div>
				</div>
				<!-- Stimuli stats -->
				<div class="card !bg-secondary-800 variant-glass p-4 flex-1">
					<div class="flex flex-col justify-center items-center gap-4">
						<SvgIcons name="stimulus" title="stimulus" height="h-32" width="32" />
						<h4>4 Stimuli</h4>
					</div>
				</div>
			</div>

			<!-- How to use the system stepper -->
			<div class="card variant-glass p-4">
				<Stepper>
					<Step>
						<svelte:fragment slot="header">Get Started!</svelte:fragment>
						<p>
							Thank you for using Detection Experiment! This section serves as guide for newcomers
							of the system. Please follow each of the steps in order to create a fully functioning
							scene for players to play.
						</p>
					</Step>
					<Step>
						<svelte:fragment slot="header">1. Create a new Stimulus.</svelte:fragment>
						<p>
							On the left sidebar, select the <b>Stimuli</b> icon. Click on the <b>Create</b> button
							and upload the picture of the stimulus. There are certain considerations when creating
							a new Stimulus. Detection Experiment does not have an image pre-processing process, so
							in order to obtain the best results, it is recommended to upload the Stimulus image as
							<b>PNG</b> and with any background removed.
						</p>
					</Step>
					<Step>
						<svelte:fragment slot="header">2. Create a new Background.</svelte:fragment>
						<p>
							On the left sidebar, select the <b>Backgrounds</b> icon. Click on the <b>Create</b>
							button and upload the picture of the background. Backgrounds does not have a pre-processing
							process either but unless transparency is needed for the background, the recommended format
							to upload a background is <b>JPEG</b> since it uses less space than a
							<b>PNG</b> image.
						</p>
					</Step>
					<Step>
						<svelte:fragment slot="header">3. Create a new Scene.</svelte:fragment>
						<p>
							This step does not require to upload any files. You have to select any of the previous <b
								>Stimulus</b
							>
							and <b>Background</b> create in order to create a new <b>Scene</b>. Please provide the
							maximum time the player have to find the <b>Stimulus</b> on the <b>Scene</b>. If a
							combination of <b>Stimulus</b> and <b>Background</b> already exists, the <b>Scene</b> cannot
							be created.
						</p>
					</Step>
				</Stepper>
			</div>
		</div>

		<!-- Second column -->
		<div class="card variant-glass">
			<!-- Table header -->
			<div class="card-header">
				<h2>Latest Scenes Created</h2>
			</div>
			<hr class="mt-2 mx-4" />

			<!-- Table content -->
			<div class="card-content">
				<div class="table-container">
					<table class="table table-hover">
						<thead>
							<tr>
								<th>Scene</th>
								<th>Stimulus</th>
								<th>Background</th>
								<th>Play Time</th>
							</tr>
						</thead>
						<tbody>
							<tr>
								<td>Amazonian Forest</td>
								<td>Green Frog</td>
								<td>Mud with leaves</td>
								<td>90 seconds</td>
							</tr>
						</tbody>
					</table>
				</div>
			</div>
		</div>
	</div>
{/if}
