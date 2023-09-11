<script>
	import { onMount } from 'svelte';
	import DriverLeaderboard from '../components/drivers/driver-leaderboard.svelte';
	import DriverDetails from '../components/drivers/driver-details.svelte';
    import RaceDetails from '../components/races/race-details.svelte';

	let leaderboard, driverId, raceId;

	onMount(async () => {
		await import('@ui5/webcomponents-fiori/dist/FlexibleColumnLayout.js');

		leaderboard.addEventListener('driver-details-leaderboard', (event) => {
			driverId = event.detail.driverId;

			leaderboard.layout = 'TwoColumnsMidExpanded';
		});

		leaderboard.addEventListener('race-details', (event) => {
			raceId = event.detail.raceId;

			leaderboard.layout = "ThreeColumnsEndExpanded";
		})
	});
</script>

<ui5-flexible-column-layout id="leaderboard" bind:this={leaderboard}>
	<div class="col" slot="startColumn">
		<DriverLeaderboard parentElement={leaderboard} />
	</div>
	<div class="col" slot="midColumn">
		<DriverDetails {driverId} parentElement={leaderboard} />
	</div>
	<div class="col" slot="endColumn">
		<RaceDetails {raceId} />
	</div>
</ui5-flexible-column-layout>

<style>
	.col {
		height: calc(100vh - 44px);
	}
</style>
