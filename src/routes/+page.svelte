<script>
 import { onMount } from "svelte";

 let leaderboard, driversList;

 onMount(async () => {
     await import("@ui5/webcomponents-fiori/dist/FlexibleColumnLayout.js");
     await import('@ui5/webcomponents/dist/list.js');

     driversList.addEventListener("item-click", () => {
         leaderboard.layout = "TwoColumnsMidExpanded";
     });
 })
</script>

<style>
 .col {
     height: calc(100vh - 44px);
 }
</style>


<ui5-flexible-column-layout id="leaderboard" bind:this={leaderboard}>
    <div class="col" slot="startColumn">
        <ui5-list header-text="Classificação geral (15 pilotos)" mode="SingleSelect" id="driversList" bind:this={driversList}>
            <ui5-li icon="slim-arrow-right" icon-end additional-text="20 pontos" additional-text-state="Success">
                1. Piloto 1
            </ui5-li>
            <ui5-li icon="slim-arrow-right" icon-end additional-text="15 pontos" additional-text-state="Information">
                2. Piloto 2
            </ui5-li>
            <ui5-li icon="slim-arrow-right" icon-end additional-text="10 pontos" additional-text-state="Warning">
                3. Piloto 3
            </ui5-li>
            <ui5-li icon="slim-arrow-right" icon-end additional-text="10 pontos">
                4. Piloto 4
            </ui5-li>
        </ui5-list>
    </div>
    <div class="col" slot="midColumn">
        <ui5-list header-text="Grand Prix (2)">
            <ui5-li>
                Corrida 1
            </ui5-li>
        </ui5-list>
    </div>

</ui5-flexible-column-layout>
