<template>
  <!-- Certificates -->
  <section id="certificates" class="py-5">
    <div class="container">
      <h2 class="text-center mb-5">My Certificates</h2>

      <div class="row g-4">

        <!-- MCP/FULL STACK CERT -->
        <div class="col-md-4">
         <a href="https://share.zertify.zuitt.co/certificate/98b59a43-3e33-45b8-93a1-fbcdc86cad3f/" target="_blank">
          <div class="certificate-card">
            <img src="/images/Zuitt Cert Full Stack.jpeg" alt="Certificate 1">
            <div class="certificate-content">
              <h3>Full Stack Web Development</h3>
              <p>Zuitt Coding Bootcamp Certificate</p>
            </div>
          </div>
          </a>
        </div>

        <!-- JS CERT -->
        <div class="col-md-4">
         <a href="https://share.zertify.zuitt.co/certificate/87c3c7fc-48c7-4e09-89e7-4be0f9d034d6/" target="_blank">
          <div class="certificate-card">
            <img src="/images/Zuitt Cert JS PREP.jpeg" alt="Certificate 2">
            <div class="certificate-content">
              <h3>Javascript Fundamentals</h3>
              <p>Zuitt Coding Bootcamp Certificate</p>
            </div>
          </div>
         </a>
        </div>

        <!-- MYSQL SC CERT -->
        <div class="col-md-4">
         <a href="https://share.zertify.zuitt.co/certificate/638d5b7d-92e6-4b84-9e45-1c5bea77ae03" target="_blank">
          <div class="certificate-card">
            <img src="/images/Zuitt Cert JS PREP.jpeg" alt="Certificate 3">
            <div class="certificate-content">
              <h3>Intro to MySQL</h3>
              <p>Zuitt Coding Bootcamp Certificate</p>
            </div>
          </div>
          </a>
        </div>

        <!-- JAVA SC CERT -->
        <div class="col-md-4">
         <a href="http://share.zertify.zuitt.co/certificate/3abbd76c-837c-4c2c-8b71-ad907465641e" target="_blank">
          <div class="certificate-card">
            <img src="/images/Zuitt Cert Intro Java.jpeg" alt="Certificate 3">
            <div class="certificate-content">
              <h3>Intro to Java</h3>
              <p>Zuitt Coding Bootcamp Certificate</p>
            </div>
          </div>
          </a>
        </div>

        <!-- SPRINGBOOT SC CERT -->
        <div class="col-md-4">
         <a href="http://share.zertify.zuitt.co/certificate/3abbd76c-837c-4c2c-8b71-ad907465641e" target="_blank">
          <div class="certificate-card">
            <img src="/images/Zuitt Cert Intro SpringBoot.jpeg" alt="Certificate 3">
            <div class="certificate-content">
              <h3>Intro to SpringBoot</h3>
              <p>Zuitt Coding Bootcamp Certificate</p>
            </div>
          </div>
          </a>
        </div>

        <!-- PYTHON SC CERT -->
        <div class="col-md-4">
         <a href="https://share.zertify.zuitt.co/certificate/cd135d6a-21a1-464b-bf73-ab7e1e0590bc/" target="_blank">
          <div class="certificate-card">
            <img src="/images/Zuitt Cert Intro Python.jpeg" alt="Certificate 3">
            <div class="certificate-content">
              <h3>Intro to Python</h3>
              <p>Zuitt Coding Bootcamp Certificate</p>
            </div>
          </div>
          </a>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>

#certificates {
  background-color: white !important;
}

#certificates h2 {
  font-weight: 700;
  color: #dc8696;
  text-align: center;
  margin-bottom: 2.5rem;
}

/* animation */
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

/* card */
.certificate-card {
  background: #fff;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;

  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 0.6s ease forwards;
}

/* stagger */
.row .col-md-4:nth-child(1) .certificate-card { animation-delay: 0.1s; }
.row .col-md-4:nth-child(2) .certificate-card { animation-delay: 0.2s; }
.row .col-md-4:nth-child(3) .certificate-card { animation-delay: 0.3s; }
.row .col-md-4:nth-child(4) .certificate-card { animation-delay: 0.4s; }

/* hover */
.certificate-card:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow: 0 12px 24px rgba(0,0,0,0.2);
}

/* image */
.certificate-card img {
  width: 100%;
  height: 220px;
  object-fit: cover;
}

/* content */
.certificate-content {
  padding: 1rem;
  text-align: center;
}

.certificate-content h3 {
  font-size: 1.2rem;
  color: #b8789a;
}

.certificate-content p {
  font-size: 0.9rem;
  color: #32353a;
}

</style>