<template>
	<!-- Landing -->
	<section id="landing">
	  <div class="container-fluid p-5">
	    <div class="row my-5 align-items-center">
	      
	      <!-- Left: Text -->
	      <div class="col-md-6 px-5">
	        <h1 id="title" class="mb-5">
	          <span class="intro">Hi, I’m </span>
	          <span class="s-name">Jaycee Lavaro</span>
	        </h1>

	        <!-- Role -->
	        <p class="role" style="
	        color: #061e48 !important; 
	        font-size: 1.5rem;
	    	font-weight: 700;
	    	color: #061e48;
	    	margin-bottom: 1rem;">Full Stack Web Developer</p>

	        <!-- About Me Button -->
	        <button 
	          v-if="!showAbout" 
	          class="btn-about mt-5" 
	          @click="showAbout = true"
	        >
	          About Me
	        </button>

	        <!-- About Me Paragraph -->
	        <p v-if="showAbout" class="about-me">
	          Hallo! I’m a Full-Stack Developer and Digital Artist with a love for pixel design. 
	          I enjoy building projects where creativity meets logic — writing clean, functional code 
	          while adding artistic touches that make my work stand out. Whether it’s developing applications 
	          or crafting digital art, I always look for ways to turn ideas into something both useful 
	          and visually engaging.
	        </p>

	      </div>

	      <!-- Right: Image -->
	      <div class="col-md-5 text-center ms-md-5">
	        <img src="/images/Landing img.png" alt="Jaycee Lavaro" class="img-fluid rounded">
	      </div>

	    </div>
	  </div>
	</section>
</template>

<script>
export default {
  data() {
    return {
      showAbout: false
    }
  }
}
</script>

<style scoped>
	#landing {
    background: white !important;
    color: #fff;
    min-height: 100vh;
    display: flex;
    align-items: center;
}

	/* Container adjustments */
	#landing .row {
	    align-items: center;
	    min-height: 80vh;
	}

	/* Name (Title) */
	#landing h1 {
	    font-size: 3.5rem;
	    font-weight: 700;
	    color: #dc8696; /* soft highlight for your name */
	    margin-bottom: 0.5rem;
	    font-family: "Solano Gothic MVB", sans-serif;
	}

	.intro {
	  font-size: 2.5rem;
	  font-weight: 500;
	  color: #061e48;
	  margin-right: 8px;
	}

	.s-name {
	  position: relative;
	  display: inline-block;
	}

	/* The underline image */
	.s-name::before {
	  content: "";
	  background-image: url("./images/line.png");
	  background-position: center;
	  background-size: contain;
	  background-repeat: no-repeat;

	  position: absolute;
	  left: -10%;             /* start from left */
	  bottom: -18%;
	  height: 22px;
	  width: 0;            /* start width 0 for animation */

	  animation: writeLine 0.8s ease-out forwards;  /* run animation */
	}

	@keyframes writeLine {
	  0% {
	    width: 0;           /* start with no line */
	    opacity: 0;         /* optional: fade in */
	  }
	  100% {
	    width: 300px;       /* full width of your line */
	    opacity: 1;
	  }
	}

	/* Role */
	#landing p:first-of-type {
	    font-size: 1.5rem;
	    font-weight: 600;
	    color: #061e48;
	    margin-bottom: 1rem;
	}

	/* Description */
	#landing p:last-of-type {
	    font-size: 1.1rem;
	    line-height: 1.6;
	    max-width: 700px;
	    color: #32353a;

	    font-family: "Poppins", sans-serif;
	      font-weight: 300;
	      font-style: normal;
	}


	.btn-about {
	  display: inline-block;
	  padding: 0.6rem 1.5rem;
	  font-size: 1.1rem;
	  font-weight: 400;
	  border: none;
	  border-radius: 8px;
	  color: white;
	  cursor: pointer;
	  background: linear-gradient(
	    to right top,
	    #facdb6,
	    #ecabc9,
	    #d1b4d8,
	    #a4c7ec
	  );
	  transition: transform 0.2s ease, box-shadow 0.2s ease;
	  margin-bottom: 1rem;
	}

	.btn-about:hover {
	  transform: scale(1.05);
	  box-shadow: 0 5px 15px rgba(0,0,0,0.3);
	}


	/* Add subtle animation */
	#landing h1, 
	#landing p {
	    animation: fadeInUp 1s ease both;
	}

	#landing img {
	    max-width: 90%;
	    margin-top: 40px;
	    height: auto;
	    border-radius: 15px;
	    box-shadow: 0 8px 20px rgba(0,0,0,0.3);
	    transition: transform 0.3s ease;
	    background: linear-gradient(
        to right top,
        #facdb6,   /* yellow */
        #ecabc9,   /* pink */
        #d1b4d8,   /* purple */
        #a4c7ec    /* blue */
    );
	}

	#landing img:hover {
	    transform: scaleX(-1) scale(1.05);
	}


	@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
	.about-me {
	  animation: fadeInUp 0.8s ease both;
	}

</style>