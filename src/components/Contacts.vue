<template>
  <!-- Contact Section -->
  <section id="contact">
    <div class="container-fluid d-flex flex-column">

      <!-- Form Row -->
      <div class="row justify-content-center align-items-center flex-grow-1">

        <div class="col-md-6 d-flex flex-column justify-content-center align-items-center p-4"
             style="background: linear-gradient(
               to right top,
               #facdb6,
               #ecabc9,
               #d1b4d8,
               #a4c7ec
             ); border-radius: 15px;">

          <h2 class="mb-4">Contact Me</h2>

          <form @submit.prevent="submitForm" class="contact-form w-100">

            <!-- Name -->
            <div class="mb-3">
              <label for="name" class="form-label">Name</label>
              <input v-model="name" type="text" class="form-control" id="name" placeholder="Enter your name" required>
            </div>

            <!-- Email -->
            <div class="mb-3">
              <label for="email" class="form-label">Email</label>
              <input v-model="email" type="email" class="form-control" id="email" placeholder="Enter your email" required>
            </div>

            <!-- Message -->
            <div class="mb-3">
              <label for="message" class="form-label">Message</label>
              <textarea v-model="message" class="form-control" id="message" rows="4" placeholder="Write your message" required></textarea>
            </div>

            <!-- Button + Social Icons -->
            <!-- Button + Social Icons -->
            <div class="d-flex flex-wrap align-items-center justify-content-between mt-3 w-100">
              <button type="submit" class="btn btn-dark" :disabled="isLoading">
                {{ isLoading ? "Sending..." : "Send" }}
              </button>

              <div class="d-flex flex-column gap-2 social-icons">
                <!-- Row 1: Social Media -->
                <div class="d-flex gap-2">
                  <!-- LinkedIn -->
                  <a href="https://www.linkedin.com/in/jc-lavaro-a06471382/" target="_blank">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" alt="LinkedIn">
                  </a>
                  <!-- GitHub -->
                  <a href="https://github.com/Jaycee1321" target="_blank">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub">
                  </a>
                  <!-- Upwork -->
                  <a href="https://upwork.com/freelancers/~0160f51a3c44480f72" target="_blank">
                    <img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/upwork.svg" alt="Upwork" style="width: 40px; height: 40px;">
                  </a>
                  <!-- WhatsApp -->
                  <a href="https://wa.me/qr/JHQEOQENDZD6J1" target="_blank">
                    <img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/whatsapp.svg" alt="WhatsApp" style="width: 40px; height: 40px;">
                  </a>
                </div>
              </div>
            </div>

            <!-- reCAPTCHA + Contact Info Aligned -->
            <div class="mt-5 w-100 d-flex justify-content-between align-items-center">
              <!-- Contact Info -->
              <div class="contact-info" style="font-size: 0.95rem; color: #32353a;">
                <span>Email: jayceel1321@gmail.com</span><br>
                <span>Phone: +63 991 688 5983</span>
              </div>

              <!-- reCAPTCHA -->
              <div ref="recaptchaContainer" style="min-height: 78px; width: 304px;"></div>
            </div>


          </form>
        </div>

      </div>

      <!-- Footer -->
      <footer class="mt-auto">
        <p>Jaycee Lavaro</p>
        <p>Full Stack Web Developer</p>
        <p>© 2025 | All rights reserved.</p>
      </footer>

    </div>
  </section>
</template>


<script setup>
import { ref, onMounted } from "vue";
import { Notyf } from 'notyf';
import 'notyf/notyf.min.css';

// --- Form data ---
const name = ref("");
const email = ref("");
const message = ref("");
const isLoading = ref(false);

// Notyf instance for notifications
const notyf = new Notyf();

// --- Web3Forms Access Key ---
const WEB3FORMS_ACCESS_KEY = "d3259b9b-d8b5-4e15-803a-0fc37e7a26e6";

// --- reCAPTCHA setup ---
const SITE_KEY = '6LdnVUksAAAAAF2SPMN07TM0WVgMjNzXRn2aGTZm';
const recaptchaContainer = ref(null);
const recaptchaWidgetId = ref(null);
const recaptchaToken = ref('');

// --- Callbacks ---
function onRecaptchaSuccess(token) {
  recaptchaToken.value = token;
}

function onRecaptchaExpired() {
  recaptchaToken.value = '';
}

// Render the reCAPTCHA widget
function renderRecaptcha() {
  if (!window.grecaptcha) return;
  recaptchaWidgetId.value = window.grecaptcha.render(recaptchaContainer.value, {
    sitekey: SITE_KEY,
    size: 'normal', // or 'compact'
    callback: onRecaptchaSuccess,
    'expired-callback': onRecaptchaExpired,
  });
}

// Reset reCAPTCHA
function resetRecaptcha() {
  if (recaptchaWidgetId.value !== null) {
    window.grecaptcha.reset(recaptchaWidgetId.value);
    recaptchaToken.value = '';
  }
}

// Dynamically load reCAPTCHA script
function loadRecaptchaScript() {
  return new Promise((resolve, reject) => {
    if (window.grecaptcha) return resolve();
    const script = document.createElement('script');
    script.src = 'https://www.google.com/recaptcha/api.js?render=explicit';
    script.async = true;
    script.defer = true;
    script.onload = () => resolve();
    script.onerror = () => reject('Failed to load reCAPTCHA script');
    document.head.appendChild(script);
  });
}

// --- Lifecycle ---
onMounted(async () => {
  try {
    await loadRecaptchaScript();
    renderRecaptcha();
  } catch (err) {
    console.error(err);
  }
});

// --- Form submission ---
const submitForm = async () => {
  if (!recaptchaToken.value) {
    notyf.error('Please verify that you are not a robot.');
    return;
  }

  isLoading.value = true;

  try {
    const response = await fetch("https://api.web3forms.com/submit", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Accept: "application/json",
      },
      body: JSON.stringify({
        access_key: WEB3FORMS_ACCESS_KEY,
        name: name.value,
        email: email.value,
        message: message.value,
        "captcha": recaptchaToken.value
      }),
    });

    const result = await response.json();

    if (result.success) {
      notyf.success("Message Sent!");
      name.value = "";
      email.value = "";
      message.value = "";
      resetRecaptcha();
    } else {
      throw new Error("Submission failed");
    }
  } catch (error) {
    console.error(error);
    notyf.error("Failed to send message.");
  } finally {
    isLoading.value = false;
  }
};
</script>


<style scoped>
#contact {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  background: #fff;
  color: #000;
}

.contact-form {
  width: 100%;
  max-width: 600px;
}

#contact .row {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-grow: 1; /* fills space to push footer down */
}

#contact h2 {
  color: white;
  font-weight: 700;
  text-align: center;
}

.form-label {
  font-weight: 600;
  color: #32353a;
}

.form-control {
  border-radius: 8px;
  border: 1px solid #ccc;
  font-family: Poppins, sans-serif;
  font-weight: 300;
}

.btn-dark {
  background: #32353a;
  color: #fff;
  font-weight: 600;
  border-radius: 30px;
  padding: 10px 24px;
  transition: all 0.3s ease;
}

.btn-dark:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 12px rgba(0,0,0,0.25);
}

.social-icons {
  display: flex;
  gap: 10px;
  align-items: center;
}

.social-icons img {
  width: 40px;
  height: 40px;
  object-fit: contain;
  transition: transform 0.3s ease, filter 0.3s ease;
}

.social-icons img:hover {
  transform: scaleX(-1) scale(1.05);
}

#contact [ref="recaptchaContainer"] {
  min-height: 78px;
  width: 100%;
  display: flex;
  justify-content: flex-end;
}

footer {
  color: rgba(50, 53, 58, 0.8);
  font-family: "Archivo Black", sans-serif;
  font-size: 16px;
  text-align: center;
  padding: 20px 0;
  margin-top: auto; /* stick footer to bottom */
}
</style>