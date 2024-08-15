<template>
    <div class="event-details">
      <div class="loading-overlay" v-if="isLoading">
        <div class="loading-spinner"></div>
        <p>Loading...</p>
      </div>
      <div v-else>
        <div v-if="event" class="event-info">
          <h1>{{ event.title }}</h1>
          <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
          <img :src="event.imageUrl" alt="Event Image" v-if="event.imageUrl" class="event-image">
          <p>{{ event.description }}</p>
        </div>
        <div v-else-if="isError" class="error-message">
          <p>Failed to fetch event details. Please try again later.</p>
        </div>
        <div v-else class="empty-message">
          <p>No event details available.</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import EventService from "@/services/EventService.js";
  
  export default {
    props: ['id'],
    data() {
      return {
        event: null,
        isLoading: true,
        isError: false
      };
    },
    created() {
      EventService.getEvent(this.id)
        .then(response => {
          this.event = response.data;
        })
        .catch(error => {
          console.log(error);
          this.isError = true;
        })
        .finally(() => {
          this.isLoading = false;
        });
    }
  };
  </script>
  
  <style scoped>
  .event-details {
    padding: 20px;
    text-align: center;
    background: linear-gradient(135deg, #000000, #333333);
    color: #fff;
  }
  
  .loading-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 999; /* Ensure it appears above other content */
  }
  
  .loading-spinner {
    border: 4px solid rgba(255, 255, 255, 0.3);
    border-radius: 50%;
    border-top: 4px solid #fff;
    width: 50px;
    height: 50px;
    animation: spin 1s linear infinite;
  }
  
  @keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }
  
  .event-info, .error-message, .empty-message {
    margin-top: 20px;
  }
  
  .event-info h1 {
    font-size: 2.5rem;
    color: #2196F3;
  }
  
  .event-info p {
    font-size: 1.1rem;
    color: #F5F5F5;
    margin-bottom: 10px;
  }
  
  .event-image {
    width: 100%;
    max-width: 400px;
    margin-top: 20px;
  }
  
  .error-message {
    color: red;
  }
  </style>
  