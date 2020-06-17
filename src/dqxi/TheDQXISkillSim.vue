<!-- 
    This file contains the template for...
-->


<template>
    <div>
        <the-page-layout>
            <the-header v-slot: header>
                <the-logo-and-info v-slot: logo-and-info> <!-- logo and info div -->
                    <button class="home_button" onclick="location.href='../index.html'">Home</button>
                    <img src="../resources/dragon-quest-xi-logo.png" height="100px" /> <!--120px, changed for testing purposes-->
                    <br>
                    <div class="info">
                        DQXI Skill Simulator by 
                        <a href="https://github.com/radiantmemories451" style="color: #ACFFE5;" target="_blank">PSIDefenseUp</a>
                    </div>
                </the-logo>
                
                <template v-slot: header-main-grid>
                    <div class = "header-main-grid">
                        <!-- the following is copy-pasted from original, check for correctness -->

                        <!-- row 1 -->
                        <div class="char_lvls_header">
                            Level
                        </div>

                        <BaseCharLvls v-for= "char in charList"
                            v-bind: key = "charList.charName" v-bind: name = "charList.charName"
                        >
                        </BaseCharLvls>


                         <!-- row 1 -->
                        <div class="game_progress_header">
                            Game Progress
                        </div>

                        <!-- row 2 -->
                        <div class="game_progress_act1_header">
                            Act 1
                        </div>

                        <div class="game_progress_act2_header">
                            Act 2
                        </div>

                        <div class="game_progress_act3_header">
                            Act 3
                        </div>

                        <!-- row 3 -->
                        <!-- more stuff goes here -->
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
    import BaseCharLvls from './BaseCharLvls.vue';

    //following was copy-pasted and then modified, might need more modification. Check to see waht export default is.
    export default {
        components: {
            BaseCharLvls,
        }, //components

        data() {
            return {
                charList: [
                    {
                    charName: 'Luminary',
                    },
                    {
                    charName: 'Erik',
                    },
                    {
                    charName: 'Veronica',
                    },
                    {
                    charName: 'Serena',
                    },
                    {
                    charName: 'Sylvando',
                    },
                    {
                    charName: 'Jade',
                    },
                    {
                    charName: 'Rab',
                    },
                    {
                    charName: 'Hendrik',
                    },
                ],
                eventListAct1: [
                    {
                        eventName: "act1event1"
                    },
                    {
                        eventName: "act1event2"
                    },
                    {
                        eventName: "act1event3"
                    },
                    {
                        eventName: "act1event4"
                    },
                ],
                eventListAct2: [
                    {
                        eventName: "act2event1"
                    },
                    {
                        eventName: "act2event2"
                    },
                    {
                        eventName: "act2event3"
                    },
                    {
                        eventName: "act2event4"
                    },
                    {
                        eventName: "act2event5"
                    },
                    {
                        eventName: "act2event6"
                    },
                    {
                        eventName: "act2event7"
                    },
                    {
                        eventName: "act2event8"
                    },
                    {
                        eventName: "act1event9"
                    },
                    {
                        eventName: "act1event10"
                    },
                    {
                        eventName: "act1event11"
                    },
                ],
                eventListAct3: [
                    {
                        eventName: "act3event1"
                    },
                    {
                        eventName: "act3event2"
                    },
                    {
                        eventName: "act3event3"
                    },
                    {
                        eventName: "act3event4"
                    },
                    {
                        eventName: "act3event5"
                    },
                    {
                        eventName: "act3event6"
                    },
                    {
                        eventName: "act3event7"
                    },
                    {
                        eventName: "act3event8"
                    },
                    {
                        eventName: "act3event9"
                    }
                ]
            };
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

    .title {
        grid-area: title;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 2.4vh;
        font-weight: bolder;
        color: rgb(44, 105, 155); /* placeholder, try rgb(44, 105, 155) */
        text-decoration: underline rgb(214,129,0) solid;
        background: url(../resources/dragon-quest-xi-title-background.png) no-repeat;
        background-position: 47%; /*89% for v1, 91% for v2, but need to get it to 60% for both% */
        background-size: 25% 100%;
    }

    .char_lvls_header {
        grid-area: char_lvls_header;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 2.3vh;
        font-weight: bolder;
    }

    .game_progress_header {
        grid-area: game_progress_header;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 2.3vh;
        font-weight: bolder;
    }

    .game_progress_act1_header {
        grid-area: game_progress_act1_header;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 2.1vh;
        font-weight: bold;
        border-bottom: 1px solid rgb(214,129,0);
    }

    .game_progress_act2_header {
        grid-area: game_progress_act2_header;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 2.1vh;
        font-weight: bold;
        text-decoration: underline rgb(214,129,0) solid;
    }

    .game_progress_act3_header {
        grid-area: game_progress_act3_header;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 2.1vh;
        font-weight: bold;
        text-decoration: underline rgb(214,129,0) solid;
    }

    .game_progress_act1_content {
        grid-area: game_progress_act1_content;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 1.7vh;
        font-weight: bold;
    }

    .game_progress_act2_content {
        grid-area: game_progress_act2_content;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 1.7vh;
        font-weight: bold;
    }

    .game_progress_act3_content {
        grid-area: game_progress_act3_content;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 1.7vh;
        font-weight: bold;
    }


    /* act 1 popup */
    .game_progress_act1_popup {
        flex-grow: 1;
        flex-basis: 100%;
        display: grid;
    
        grid-template-areas:
            "game_progress_act1_header"
            "."
            "."
            "."
            ".";
            
        grid-template-columns: 1fr;
        grid-template-rows: 0.3fr 0.3fr 0.3fr 0.3fr 0.3fr;
        /* border: 3px solid rgb(214,129,137); */
    }

    #game_progress_act1_popup {
        display: none;
        position: fixed; /* Stay in place */
        z-index: 1; /* Sit on top */
        left: 0;
        top: 0;
        width: 100%; /* Full width */
        height: 100%; /* Full height */
        overflow: auto; /* Enable scroll if needed */
        background-color: rgb(0,0,0); /* Fallback color */
        background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
    }


    /* act 2 popup */
    .game_progress_act2_popup {
        flex-grow: 1;
        flex-basis: 100%;
        display: grid;
    
        grid-template-areas:
            "game_progress_act2_header game_progress_act2_header game_progress_act2_header"
            ". . ."
            ". . ."
            ". . ."
            ". . .";
            
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
        grid-template-rows: 0.3 0.3fr 0.3fr 0.3fr;
        /* border: 3px solid rgb(214,129,137); */
    }

    #game_progress_act2_popup {
        display: none;
        position: fixed; /* Stay in place */
        z-index: 1; /* Sit on top */
        left: 0;
        top: 0;
        width: 100%; /* Full width */
        height: 100%; /* Full height */
        overflow: auto; /* Enable scroll if needed */
        background-color: rgb(0,0,0); /* Fallback color */
        background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
    }


    /* act 3 popup */
    .game_progress_act3_popup {
        flex-grow: 1;
        flex-basis: 100%;
        display: grid;
    
        grid-template-areas:
            "game_progress_act3_header game_progress_act3_header game_progress_act3_header"
            ". . ."
            ". . ."
            ". . .";
            
        grid-template-columns: 1fr 1fr 1fr;
        grid-template-rows: 0.3fr 0.3fr 0.3fr 0.3fr;
        /* border: 3px solid rgb(214,129,137); */
    }

    #game_progress_act3_popup {
        display: none;
        position: fixed; /* Stay in place */
        z-index: 1; /* Sit on top */
        left: 0;
        top: 0;
        width: 100%; /* Full width */
        height: 100%; /* Full height */
        overflow: auto; /* Enable scroll if needed */
        background-color: rgb(0,0,0); /* Fallback color */
        background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
    }


    /* */
    .popup_box {
        background-color: rgb(44, 105, 155);
        margin: 15% auto; /* 15% from the top and centered */
        padding: 20px;
        border: 1px solid #888;
        width: 80%; /* Could be more or less, depending on screen size */
    }

    .close_button {
    color: #aaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
    }

    .close_button:hover,
    .close_button:focus {
    color: #F2B14D;
    text-decoration: none;
    cursor: pointer;
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

    .skill_tree {
        grid-area: skill_tree;
        display: flex;
        color: #F2B14D;
        font-family: Helvetica, Arial;
    }

    .spell_chart {
        grid-area: spell_chart;
        display: flex;
        color: #F2B14D;
        font-family: Helvetica, Arial;
    }

    .ability_chart {
        grid-area: ability_chart;
        display: flex;
        color: #F2B14D;
        font-family: Helvetica, Arial;
    }

    .pep_power_chart {
        grid-area: pep_power_chart;
        display: flex;
        color: #F2B14D;
        font-family: Helvetica, Arial;
    }

    .stat_boost_chart {
        grid-area: stat_boost_chart;
        display: flex;
        color: #F2B14D;
        font-family: Helvetica, Arial;
    }
</style>