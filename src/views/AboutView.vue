<template>
  <div class="about">
    <!-- Content -->
    <div class="content">
      <h1>Welcome to the ONGC News Portal</h1>
      <p>We are dedicated to bringing you the latest news and updates from ONGC (Oil and Natural Gas Corporation Limited). Our mission is to provide accurate, reliable, and timely information to our readers.</p>
      <p>Explore our portal to stay informed about the latest developments, innovations, and events in the world of energy and beyond.</p>
      <p>Join our community of enthusiasts, professionals, and industry experts as we embark on a journey to explore the future of energy together.</p>
    </div>
    <!-- Image -->
    <div class="image-container">
      <img src="https://media.assettype.com/psuwatch%2Fimport%2Fwp-content%2Fuploads%2F2022%2F02%2Fwebp.net-compress-image-27-611108cd1e2a2-3.jpg?w=1200&auto=format%2Ccompress&fit=max" alt="ONGC Image" class="ongc-image">
    </div>
    <!-- Suggestion Box -->
    <div class="suggestion-box">
      <h2>Have any suggestions or feedback?</h2>
      <form @submit.prevent="submitSuggestion">
        <textarea v-model="suggestion" placeholder="Enter your suggestion or feedback"></textarea>
        <button type="submit">Submit</button>
      </form>
    </div>
    <!-- Feedback Success Modal -->
    <div v-if="showModal" class="modal" @click.self="closeModal">
      <div class="modal-content">
        <span class="close" @click="closeModal">&times;</span>
        <h2>Thank you for your feedback!</h2>
        <p>We appreciate your input. Your feedback has been submitted successfully.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      suggestion: '',
      showModal: false
    };
  },
  methods: {
    submitSuggestion() {
      // Here, you can implement the logic to send the suggestion to your backend or perform any other action
      console.log('Suggestion submitted:', this.suggestion);
      // You can also clear the suggestion textarea after submission
      this.suggestion = '';
      // Show the feedback success modal
      this.showModal = true;
    },
    closeModal() {
      // Close the feedback success modal
      this.showModal = false;
    }
  }
};
</script>

<style scoped>
/* Styles for the about page */
.about {
  padding: 20px;
  text-align: center;
  background: linear-gradient(135deg, #000000, #333333);
  color: #fff;
}

.content {
  margin-bottom: 40px;
}

.about h1 {
  font-size: 2.8rem;
  margin-bottom: 20px;
  color: #ffdd57;
}

.about p {
  font-size: 1.1rem;
  line-height: 1.8;
  color: #b3b3b3;
  margin-bottom: 10px;
}

.image-container {
  position: relative;
  overflow: hidden;
  max-width: 100%;
}

.ongc-image {
  width: 100%;
  max-width: 600px;
  transition: transform 0.5s ease, border-color 0.5s ease;
  border: 5px solid transparent;
}

.ongc-image:hover {
  transform: scale(1.1);
  border-color: #ffdd57;
}

.suggestion-box {
  margin-top: 40px;
}

.suggestion-box h2 {
  font-size: 1.5rem;
  margin-bottom: 10px;
  color: #fff;
}

textarea {
  width: 100%;
  height: 100px;
  resize: vertical;
  margin-bottom: 10px;
}

button {
  background-color: #ffdd57;
  color: #333;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #ffc107;
}

/* Styles for the feedback success modal */
.modal {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 999;
}

.modal-content {
  background-color: #fff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
  position: relative; /* Added to make the close button absolute relative to the modal content */
}

.close {
  position: absolute;
  top: 10px;
  right: 10px;
  cursor: pointer;
  font-size: 1.5rem;
  color: #999;
}

.close:hover {
  color: #333;
}
</style>
