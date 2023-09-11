<script>
 import { onMount } from 'svelte';
 import RaceCard from './race-card.svelte';

 onMount(async () => {
	 await import('@ui5/webcomponents/dist/Title');
	 await import('@ui5/webcomponents-fiori/dist/Page.js');
     await import("@ui5/webcomponents-fiori/dist/Bar.js");
 });

 export let driverId, parentElement;

</script>

<style>
 .driverRaces {
     width: 100%;
     height: 100%;
     display: grid;
     grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
     gap: 15px 20px;
     padding: 20px 10px;
 }
</style>

<ui5-page background-design="List">
	<ui5-bar class="driverDetailsHeader" slot="header" design="Header">
		<ui5-title level="H3">{driverId}</ui5-title>
	</ui5-bar>
    <div class="driverRaces">
        <RaceCard podium={['Ricardi', 'Ricardois', 'Ricartres']} {parentElement} driverPosition={2} trackName="Interlagos" raceDate="16/08/2023" />
    </div>
</ui5-page>
