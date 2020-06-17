<!-- 
    This file contains the template for...
-->


<template>
    <div>
        <the-page-layout>
            <the-header v-slot: header>
                <the-logo-and-info v-slot: logo-and-info> <!-- logo and info div -->
                    
                </the-logo-and-info>
                
                <template v-slot: header-main-grid>
                    <div class = "header-main-grid">
                        <!-- -->
                    </div>
                </template>
                
                <the-header-links v-slot: header-links></the-header-links>
            <the-header>

            <the-nav-tabs v-slot: nav-tabs>
                <!-- See here for flexbox menu with components: https://michaelnthiessen.com/reducing-redundant-repetition/ -->
            </the-nav-tabs>

            <main v-slot: main>
                <!-- -->
            </main>
        </the-page-layout>
    </div>
</template>


<script>

    export default {
        components: {
            //
        }, //components

        data() {
            return {
                //
            }
        },
    }
</script>


<style scoped>
    /**************/
    /*  Heading   */
    /**************/
    /* Contains the main content of the header */
    .header_main_grid {
        display: inline-grid;
        flex-grow: 1;
        flex-basis: 100%;
    
        grid-template-areas:
            "title title title title title title title"
            "char_lvls_header char_lvls_header char_lvls_header char_lvls_header game_progress_header game_progress_header game_progress_header"
            ". . . . game_progress_act1_header game_progress_act2_header game_progress_act3_header"
            ". . . . game_progress_act1_content game_progress_act2_content game_progress_act3_content";

            /*
            "char_lvls_header char_lvls_header char_lvls_header char_lvls_header game_progress_header game_progress_header game_progress_header"
            "char_lvls_Luminary char_lvls_Erik char_lvls_Veronica char_lvls_Serena game_progress_act1_header game_progress_act2_header game_progress_act3_header"
            "char_lvls_Sylvando char_lvls_Jade char_lvls_Rab char_lvls_Eight game_progress_act1_content game_progress_act2_content game_progress_act3_content";
            */

        grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
        grid-template-rows: 3fr 0.3fr 0.3fr 0.3fr;
        /* border: 3px solid rgb(214,129,137); */
    }

    .header_main_grid > * {
        /* border: 1px solid rgb(214,129,0); */
    }

    /**************/
    /*    Main    */
    /**************/
    /* Grid containing the main content of the body */
    .main_grid {
        /* grid fallback (if grid not supported) */

        /* if supported */
        flex-grow: 1;
        flex-basis: 100%;
        display: inline-grid;
    
        grid-template-areas:
            "skill_tree spell_chart"
            "skill_tree ability_chart"
            "skill_tree pep_power_chart"
            "skill_tree stat_boost_chart";
    
        grid-template-columns: 3fr 1fr;
        grid-template-rows: 1fr 1fr 1fr 1fr;
    }

    .main_grid > * {
        border: 1px solid rgb(214,129,0);
    }


</style>