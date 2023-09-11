<script>
 import { onMount } from 'svelte';

 onMount(async () => {
	 await import('@ui5/webcomponents/dist/Title');
	 await import('@ui5/webcomponents-fiori/dist/Page.js');
     await import("@ui5/webcomponents-fiori/dist/Bar.js");
 });

 export let raceId;
</script>

<ui5-page background-design="List">
    <ui5-bar class="raceDetailsHeader" slot="header" design="Header">
		<ui5-title level="H3">{raceId}</ui5-title>
	 </ui5-bar>
</ui5-page>
