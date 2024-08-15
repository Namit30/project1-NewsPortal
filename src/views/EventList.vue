<template>
  <div class="dashboard">
    <h1>ONGC NEWS DASHBOARD</h1>
    <img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ELMWyWnc0BTwPxZGZFCIaQ.png" alt="welcome" height="200" class="center"/>
    <div class="content">
      <div class="events">
        <EventCard v-for="event in events" :key="event.id" :event="event"/>
      </div>
      <div class="footer-line"></div> <!-- Adding a separating line -->
      <div class="footer">
        <p>Thanks for visiting! Do visit again for more news updates.</p>
        <p>Contact us:</p>
        <p>Email: <a href="mailto:namit752@gmail.com">namit752@gmail.com</a></p>
        <p>Mobile: <a href="tel:+917678605936">7678605936</a></p>
      </div>
    </div>
  </div>
</template>

<script>
import EventCard from "@/components/EventCard.vue";
import EventService from "@/services/EventService.js";

export default {
  name: "Dashboard",
  components: {
    EventCard
  },
  data() {
    return {
      events: []
    };
  },
  created() {
    EventService.getEvents()
      .then(response => {
        this.events = response.data;
      })
      .catch(error => {
        console.log(error);
      });
  }
};
</script>

<style scoped>
.dashboard {
  padding: 20px;
  background: linear-gradient(135deg, #f5f5f5, #cccccc);

}

.dashboard h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
  color: #333;

}

.center {
  margin: 20px auto;
  display: block;
}

.content {

  padding: 20px;
  border-radius: 10px;
  margin-top: 20px;
}

.events {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  justify-items: center;
}

.footer-line {
  margin-top: 20px;
  border-top: 1px ;
}

.footer {
  margin-top: 20px;
  color: #fff;
  background: linear-gradient(135deg, #333333, #666666);
 /* Black gradient background */
  padding: 20px;
}

.footer p {
  margin-bottom: 10px;
}
</style>
