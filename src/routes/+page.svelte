<script lang='ts'>
    import AgGrid from '$lib/ag-grid/ag-grid.svelte';
    import type { GridOptions } from '@ag-grid-community/core';

    let gridOptions: GridOptions = {
        columnDefs: [
            { 'headerName': "Hello World" }
        ]
    }
</script>

<AgGrid gridOptions={gridOptions}></AgGrid>