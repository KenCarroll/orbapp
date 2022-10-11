
<template>
    <v-row>
      <div id="graph"></div>
    </v-row>
  </template>
  
  <script>
  import Orb from '@memgraph/orb';
  export default {
    name: 'InspirePage',
    mounted() {
    const container = document.getElementById("graph");
    
    const nodes = [
      { id: 1, label: "Orb" },
      { id: 2, label: "Graph" },
      { id: 3, label: "Canvas" },
    ];
    const edges = [
      { id: 1, start: 1, end: 2, label: "DRAWS" },
      { id: 2, start: 2, end: 3, label: "ON" },
    ];
    
    // First `Orb` is just a namespace of the JS package 
    const orb = new Orb(container);
    
    // Initialize nodes and edges
    orb.data.setup({ nodes, edges });
    
    // Render and recenter the view
    orb.view.render(() => {
      orb.view.recenter();
    });
  },
  }
  </script>
