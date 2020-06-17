<!-- 
    This file contains the template for the
    basic layout for every skill simulator.
-->


<template>
    <div class="page-grid">
        <header class="header">
            <slot name="header"></slot>
        </header>

        <slot name=""></slot>

        <div class="nav-tabs">
            <slot name="nav-tabs"></slot>
        </div>

        <div class="main">
            <slot name="main"></slot>
        </div>

        <footer class="footer">
            <slot name="footer"></slot>
        </footer>
    </div>
</template>


<script>
    //
</script>


<style scoped>
    /**********************/
    /*  CSS Grid Layouts  */
    /**********************/
    /*Page layout for every skill simulator*/
    .page_grid {
        /* grid fallback (if grid not supported) */

        /* if supported */
        display: grid;
    
        grid-template-areas:
            "header"
            "nav-tabs"
            "main"
            "footer";
    
        grid-template-columns: 1fr;
        grid-template-rows: 0.8fr 0.3fr 4fr 0.5fr;
        grid-gap: 0px;
        height: 100vh;
    }

    /*
    .page_grid > * {
        border: 3px solid rgb(37, 24, 156);
    }
    */

    .header {
        grid-area: header;
        background-color: var(--header-background);
        flex-grow: 0;
        display: flex;
        flex-direction: row;
        padding: 10px;
        font-family: Georgia, 'Times New Roman', Times, serif;
    }

    .nav-tabs {
        grid-area: nav-tabs;
        background-color: var(--header-background);
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-around;
        align-items: center;
        margin: 0;
        padding: 0.05% 0.03% 0 0.026%;
        list-style: none;
        border-bottom: 2px solid var(--header-background);
    }

    .main {
        /* grid fallback (if grid not supported) */
        display: flex;
        flex-wrap: none;

        /* if supported */
        grid-area: main;
        display: flex;
        justify-content: space-around;
        flex-direction: column;
        align-items: center;
    }

    .footer {
        grid-area: footer;
    }
</style>