/**
 * Author:    Davi Bacalhau (littlesekii)
 * Purpose:   Understand and use Vue 3 v-for directive. 
 * 
 **/

 <script setup>
 import { reactive, ref } from 'vue';
 
 const name = ref("Davi Bacalhau");
 const age = ref(22);
 
 const playedGames = reactive([
     {
         name: "Chrono Trigger",
         launchYear: 1995
     },
     {
         name: "The Legend of Zelda: Tears of the Kingdom",
         launchYear: 2023
     },
     {
         name: "Shadow of the Colossus",
         launchYear: 2005
     }
 ]);
 
 </script>
 
 <template>
     <div class="container">
         
         <h1>Player ID</h1>

         <!-- Array loop -->
         <div class="player-container">
             <div class="player-info">
                 <h2>{{ name }}</h2>  
                 <h5>{{ age }} years</h5>  
             </div>
             <div class="player-gamelist">
                 <ul>
                    <li> 
                        only data (Array loop)
                    </li>
                     <li v-for="playedGame in playedGames"> 
                        ({{ playedGame.launchYear }}) {{ playedGame.name }} 
                    </li>
                 </ul>
             </div>
         </div>

         <h2>Another uses</h2>
         
         <!-- Array loop w/ keys -->
         <div class="player-container">
            <div class="player-gamelist">
                 <ul>
                    <li> 
                        key - data (Array loop)
                    </li>
                    <li v-for="playedGame, key in playedGames"> 
                        {{ key }} - {{ playedGame.name }} 
                    </li>
                 </ul>
             </div>
         </div>

         <!-- Object loop -->
         <div class="player-container">
            <div class="player-gamelist">
                 <ul>
                    <li> 
                        only data (Object loop)
                    </li>
                    <li v-for="data in playedGames[0]"> 
                        {{ data }} 
                    </li>
                 </ul>
             </div>
         </div>

         <!-- Object loop w/ keys -->
         <div class="player-container">
            <div class="player-gamelist">
                 <ul>
                    <li> 
                        key - data (Object loop)
                    </li>
                    <li v-for="data, key in playedGames[0]"> 
                        {{ key }} - {{ data }} 
                    </li>
                 </ul>
             </div>
         </div>


     </div>
 
 </template>
 
 <style scoped>
    .container {
        display: flex;
        flex-direction: column;

        justify-content: center;
        align-items: center;
    }
    .container > h1 {
        margin-bottom: 20px;
    }
    .container > h2 {
        margin-top: 20px;
        margin-bottom: 20px;
    }

    .player-container {
        width: 100%;
        max-width: 410px;
        padding: 10px;
        margin-bottom: 20px;

        border: 2px solid var(--black-light);
    }

    .player-info {
        padding-bottom: 10px;
        margin-bottom: 10px;
        
        border-bottom: 1px solid var(--black-light);
    }

    .player-gamelist ul {
        list-style: none;
        padding: 0px;
        padding: 10px;
    }
    .player-gamelist ul li {
        padding-bottom: 5px;
    }
    .player-gamelist ul li:first-child {
        padding-bottom: 20px;
    }
    .player-gamelist ul li:last-child {
        padding: 0px;
    }
 
 </style>
 
 