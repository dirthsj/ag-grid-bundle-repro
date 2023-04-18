<script lang="ts">
    import type { Grid, GridOptions } from "@ag-grid-community/core";
    import { createEventDispatcher, onMount } from "svelte";

    import "@ag-grid-community/styles/ag-grid.css";
    import "@ag-grid-community/styles/ag-theme-alpine.css"

    export let gridOptions: GridOptions<any>;
    
    const dispatcher = createEventDispatcher<{ 'gridReady': Grid }>();

    let container: HTMLDivElement;

    onMount(async () => {
        const { Grid } = await import('./ag-grid');
        let grid = new Grid(container, gridOptions);
        dispatcher('gridReady', grid);
    })
</script>

<div class="ag-theme-alpine" style="width: 100px; height: 100px" bind:this={container}></div>