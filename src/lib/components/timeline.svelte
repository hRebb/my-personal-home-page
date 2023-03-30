<!-- Timeline.svelte -->
<template>
    <div class="timeline">
      {#each events as event}
        <div class="timeline-item">
          <div class="timeline-date">{event.date}</div>
          <div class="timeline-content">
            <h4 class="timeline-title">{event.name}</h4>
            <p>{event.description}</p>
          </div>
        </div>
      {/each}
    </div>
  </template>
  
  <script>
    export let events;
  </script>
  
  <style>
    @import './timeline.css';
  </style>
  