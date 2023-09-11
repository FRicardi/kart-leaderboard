<script>
 import { onMount } from 'svelte';

 let raceCardHeader;

 onMount(async () => {
	 await import('@ui5/webcomponents/dist/CardHeader.js');
     await import('@ui5/webcomponents/dist/Card');
     await import('@ui5/webcomponents/dist/list.js');

     raceCardHeader.addEventListener('click', (event) => {
        const raceId = event.target.dataset.raceId;

         parentElement.dispatchEvent(
		    new CustomEvent('race-details', { detail: { raceId } })
		);
     })
 });

 export let podium, driverPosition, raceDate, trackName, parentElement;
</script>

<style>
 .driverRaceDetails {
     width: 300px;
     max-height: 300px;
 }
</style>

<ui5-card class="driverRaceDetails">
    <ui5-card-header data-race-id="1" bind:this={raceCardHeader} slot="header" title-text={trackName} subtitle-text={`Colocação: ${driverPosition}`} status={raceDate} interactive />
    <ui5-list separators="None" stye="margin-block-end: 0.75rem;">
        {#each podium as driver, index}
            <ui5-li description={ index + 1 }>{driver}</ui5-li>
        {/each}
    </ui5-list>
</ui5-card>
