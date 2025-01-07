<script setup>
import { ref } from "vue";
import Swal from "sweetalert2";

const showForm = ref(false);
const name = ref("");
const email = ref("");
const message = ref("");
const errors = ref({ name: "", email: "", message: "" });

const toggleForm = () => {
  showForm.value = !showForm.value;
};

const validateForm = () => {
  errors.value = { name: "", email: "", message: "" };
  let valid = true;

  if (!name.value.trim()) {
    errors.value.name = "Name is required.";
    valid = false;
  }
  if (!email.value.trim() || !/^\S+@\S+\.\S+$/.test(email.value)) {
    errors.value.email = "Valid email is required.";
    valid = false;
  }
  if (!message.value.trim()) {
    errors.value.message = "Message is required.";
    valid = false;
  }

  if (valid) {
    sendMessage();
  }
};

const sendMessage = () => {
  Swal.fire({
    title: "Message Sent!",
    html: `
      <p>Your message has been sent successfully.</p>
      <p><strong>Name:</strong> ${name.value}</p>
      <p><strong>Email:</strong> ${email.value}</p>
      <p><strong>Message:</strong> ${message.value}</p>
    `,
    icon: "success",
    confirmButtonText: "OK",
  });

  name.value = "";
  email.value = "";
  message.value = "";
  showForm.value = false;
};
</script>

<template>
  <div>
    <button @click="toggleForm" class="flying-button">
      <i class="fas fa-envelope"></i>
    </button>
    <div v-if="showForm" class="form-container">
      <h1 class="dh2">Contact Us</h1>
      <form @submit.prevent="validateForm">
        <div class="form-group">
          <label for="name">Your Name</label>
          <input
            type="text"
            id="name"
            v-model="name"
            placeholder="Enter your name"
          />
          <small v-if="errors?.name" class="error">{{ errors?.name }}</small>
        </div>
        <div class="form-group">
          <label for="email">Your Email</label>
          <input
            type="email"
            id="email"
            v-model="email"
            placeholder="Enter your email"
          />
          <small v-if="errors?.email" class="error">{{ errors?.email }}</small>
        </div>
        <div class="form-group">
          <label for="message">Your Message</label>
          <textarea
            id="message"
            v-model="message"
            placeholder="Enter your message"
          ></textarea>
          <small v-if="errors?.message" class="error">{{
            errors?.message
          }}</small>
        </div>
        <button type="submit" class="submit-btn">Send Message</button>
      </form>
    </div>
  </div>
</template>

<style scoped>
.flying-button {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background-color: #f4a261;
  color: white;
  font-size: 1.5rem;
  width: 60px;
  height: 60px;
  border: none;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.flying-button:hover {
  background-color: white;
  color: #e76f51;
}

.fas {
  font-size: 1.5rem;
}

.form-container {
  position: fixed;
  bottom: 100px;
  right: 20px;
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
  z-index: 9999;
  max-width: 300px;
  width: 100%;
}

.dh2 {
  color: black;
}

.form-group {
  margin-bottom: 15px;
}

form label {
  display: block;
  font-size: 1rem;
  margin-bottom: 5px;
  color: black;
}

form input,
form textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
}

form textarea {
  resize: none;
  height: 80px;
}

.error {
  color: #ff6666;
  font-size: 0.9rem;
}

.submit-btn {
  background-color: #f4a261;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.submit-btn:hover {
  background-color: #e76f51;
}
</style>
