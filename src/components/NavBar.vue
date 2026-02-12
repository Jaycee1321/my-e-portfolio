<template>
  <!-- Navbar -->
  <nav class="navbar navbar-expand-lg navbar-dark px-5">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">JAYCEE</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
              aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto align-items-center">
          <li class="nav-item"><a class="nav-link" href="#landing">Home</a></li>
          <li class="nav-item"><a class="nav-link" href="#projects">Projects</a></li>
          <li class="nav-item"><a class="nav-link" href="#tools">Tools</a></li>
          <li class="nav-item"><a class="nav-link" href="#contact">Contacts</a></li>
        </ul>

        <!-- Download CV Button -->
        <a
          href="/files/airline mockup.png" 
          class="btn-download-cv ms-3"
          target="_blank"
          download
        >
          Download CV
        </a>
      </div>
    </div>
  </nav>
</template>

<style scoped>
/* Navbar styling */
.navbar {
  background-color: #facdb6 !important;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 999;
}

.navbar-brand {
  font-weight: 700;
  font-size: 2.5rem;
  letter-spacing: 2px;
  font-family: "Solano Gothic MVB", sans-serif;
  background: linear-gradient(to right, #d0cb9c, #ecabc9, #d1b4d8, #a4c7ec);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.navbar-nav .nav-link {
  color: #dc8696 !important;
  margin: 0 10px;
  font-weight: 500;
  transition: color 0.3s ease;
}

.navbar-nav .nav-link:hover {
  background: linear-gradient(to right top, #facdb6, #ecabc9, #d1b4d8, #a4c7ec);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.navbar-toggler {
  border-color: #dc8696 !important;
}

.navbar-toggler-icon {
  background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='rgba(220,134,150, 1)' stroke-width='2' stroke-linecap='round' stroke-miterlimit='10' d='M4 7h22M4 15h22M4 23h22'/%3E%3C/svg%3E");
}

/* Pink CV Button */
.btn-download-cv {
    border: 1px solid transparent;
    padding: 0.6em 1.2em;
    font-size: 1rem;
    font-weight: 500;
    font-family: inherit;
    cursor: pointer;

    /* Pink gradient */
    background: #ecabc9;
    background: -moz-linear-gradient(0deg, rgba(236,171,201,1) 0%, rgba(241,142,184,1) 100%);
    background: -webkit-linear-gradient(0deg, rgba(236,171,201,1) 0%, rgba(241,142,184,1) 100%);
    background: linear-gradient(0deg, rgba(236,171,201,1) 0%, rgba(241,142,184,1) 100%);
    
    /* Smooth hover transition */
    transition: transform 0.25s ease, box-shadow 0.25s ease, border-color 0.25s ease;
    color: white;
    border-radius: 8px;
    text-decoration: none;
    display: inline-block;
}

.btn-download-cv:hover {
    transform: scale(1.05);
    box-shadow: 0 5px 15px rgba(236, 171, 201, 0.6);
    border-color: rgba(236,171,201,0.8);
    text-decoration: none;
    color: white;
}

</style>
