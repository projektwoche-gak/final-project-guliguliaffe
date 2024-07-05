<template>


  <v-container class="fill-height">
    <v-row no-gutters>
      <v-col cols="12" md="12" lg="12" sm="12">
        <my-first-component v-for="match in groups.firstGroupStage" :key="match.matchID" :team-one="match.team1.teamName" :team-two="match.team2.teamName" :team-one-icon="match.team1.teamIconUrl" :team-two-icon="match.team2.teamIconUrl" :match-time="match.matchDateTime"></my-first-component>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>

const { data } = await useFetch(
  "https://api.openligadb.de/getmatchdata/em/2024/"
);

 let groups = {
   firstGroupStage: [],
   secondGroupStage: [],
   thirdGroupStage: [],
   roundOf16: [],
   roundOf8: [],
   roundOf4: [],
   final: [],
 };
 
 for (const match of data.value) {
   if (match.group.groupName === "1. Runde Gruppenphase") {
     groups.firstGroupStage.push(match)
   }
   if (match.group.groupName === "2. Runde Gruppenphase") {
     groups.secondGroupStage.push(match)
   }
   if (match.group.groupName === "3. Runde Gruppenphase") {
     groups.thirdGroupStage.push(match)
   }
   if (match.group.groupName === "Achtelfinale") {
     groups.roundOf16.push(match)
   }
   if (match.group.groupName === "Viertelfinale") {
     groups.roundOf8.push(match)
   }
   if (match.group.groupName === "Halbfinale") {
     groups.roundOf4.push(match)
   }
   if (match.group.groupName === "Finale") {
     groups.final.push(match)
   }
 }




</script>


