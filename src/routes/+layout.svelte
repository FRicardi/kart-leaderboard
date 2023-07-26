<script>
 import { onMount } from "svelte";

 onMount(async () => {
     await import('@ui5/webcomponents-fiori/dist/ShellBar');
     await import('@ui5/webcomponents/dist/list.js')
 })

</script>

<ui5-shellbar primary-title="Gauchão de Kart">
    <ui5-li slot="menuItems">
        Corridas
    </ui5-li>
    <ui5-li slot="menuItems">
        Leaderboard
    </ui5-li>
</ui5-shellbar>
