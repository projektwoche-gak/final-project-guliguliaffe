<template>


  <v-expansion-panels>
    <v-expansion-panel>
      <v-expansion-panel-title v-slot="{ }">
        <v-row no-gutters>
          <v-col align="left" >
  
          <v-img
            width="50px"
            aspect-ratio="16/9"
            align="center"
           :src="props.teamOneIcon"
           >
          </v-img>
          </v-col>
            <v-col align="left"> {{props.teamOne}} vs {{props.teamTwo}}</v-col>
            <v-col align="left">
              <v-img  
                width="50px"
                aspect-ratio="16/9"
                align="center"
                :src="props.teamTwoIcon"
                >
              </v-img>
            </v-col>
            <v-col align ="right">{{props.matchTime}}</v-col>
        </v-row>
      </v-expansion-panel-title>
      <v-expansion-panel-text>
        <v-table theme="light">
          <thead>
            <tr>
              <th class="text-left">Ergebnis</th>
              <th class="text-left"></th>
              <th class="text-left">Torschütze</th>
              <th class="text-left">Minute</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in Spiel" :key="item.ergebnis">
              <th>{{ item.leer }}</th>
              <td>{{ item.ergebnis }}</td>
              <td>{{ item.torschuetze }}</td>
              <td>{{ item.minute }}</td>
            </tr>
          </tbody>
        </v-table>
      </v-expansion-panel-text>
    </v-expansion-panel>
  </v-expansion-panels>
</template>

<script setup>
const props = defineProps(['teamOne', "teamTwo", "teamOneIcon", "teamTwoIcon", "matchTime"])
</script>

<script>
export default {
   data() { return {
     Spiel: [ 
      {
          ergebnis: 'null',
          torschuetze:'null',
  	      minute: 'null', 
      },
            ], 
          }
        },
      }
</script>
