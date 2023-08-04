<script>
	import { onMount } from 'svelte';
	import DriverLeaderboard from '../components/driver-leaderboard.svelte';
	import DriverDetails from '../components/driver-details.svelte';

	let leaderboard, driverId;

	onMount(async () => {
		await import('@ui5/webcomponents-fiori/dist/FlexibleColumnLayout.js');

		leaderboard.addEventListener('driver-details-leaderboard', (event) => {
			driverId = event.detail.driverId;

			leaderboard.layout = 'TwoColumnsMidExpanded';
		});
	});
</script>

<ui5-flexible-column-layout id="leaderboard" bind:this={leaderboard}>
	<div class="col" slot="startColumn">
		<DriverLeaderboard parentElement={leaderboard} />
	</div>
	<div class="col" slot="midColumn">
		<DriverDetails {driverId} />
	</div>
</ui5-flexible-column-layout>

<style>
	.col {
		height: calc(100vh - 44px);
	}
</style>
