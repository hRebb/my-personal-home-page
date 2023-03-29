<!-- Timeline.svelte -->
<template>
    <div class="timeline">
      {#each events as event}
        <div class="timeline-item">
          <div class="timeline-date">{event.date}</div>
          <div class="timeline-content">
            <h4>{event.name}</h4>
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
    /* Styles pour la ligne de temps */
    .timeline {
      position: relative;
      max-width: 1200px;
      margin: 0 auto;
    }
    .timeline:before {
      content: '';
      position: absolute;
      top: 0;
      bottom: 0;
      width: 2px;
      background-color: #ddd;
      left: 50%;
      margin-left: -1px;
    }
    .timeline-item {
      padding: 10px 0;
      position: relative;
    }
    .timeline-date {
      position: absolute;
      top: 10px;
      left: 50%;
      transform: translateX(-50%);
      background-color: #ddd;
      padding: 5px;
      border-radius: 5px;
      font-size: 14px;
    }
    .timeline-content {
      padding: 10px;
      background-color: #f5f5f5;
      border-radius: 5px;
    }
  </style>
  