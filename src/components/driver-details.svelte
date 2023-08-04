<script>
 import { onMount } from 'svelte';

 onMount(async () => {
	 await import('@ui5/webcomponents/dist/Title');
	 await import('@ui5/webcomponents-fiori/dist/Page.js');
 });

 export let driverId;
</script>

<style>
 .driver-header {
     padding: 20px 10px
 }
</style>

<ui5-page>
	<div class="driver-header" slot="header">
		<ui5-title level="H3">{driverId}</ui5-title>
		<div>Races: 10</div>
	</div>
</ui5-page>
