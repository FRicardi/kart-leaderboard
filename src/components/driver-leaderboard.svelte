<script type="text/javascript">
 import { onMount } from "svelte";

 onMount(async () => {
     await import("@ui5/webcomponents/dist/list.js");
 })

 export let driversList;
</script>


<ui5-list header-text="Classificação geral (15 pilotos)" mode="SingleSelect" id="driversList" bind:this={driversList}>
    <ui5-li icon="slim-arrow-right" icon-end additional-text="20 pontos" additional-text-state="Success" id="piloto1">
        1. Piloto 1
    </ui5-li>
    <ui5-li icon="slim-arrow-right" icon-end additional-text="15 pontos" additional-text-state="Information" id="piloto2">
        2. Piloto 2
    </ui5-li>
    <ui5-li icon="slim-arrow-right" icon-end additional-text="10 pontos" additional-text-state="Warning" id="piloto3">
        3. Piloto 3
    </ui5-li>
    <ui5-li icon="slim-arrow-right" icon-end additional-text="10 pontos" id="piloto4">
        4. Piloto 4
    </ui5-li>
</ui5-list>
