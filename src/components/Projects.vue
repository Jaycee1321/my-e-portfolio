<template>
	<!-- Projects -->
	<section id="projects" class="py-5">
	  <div class="container">
	    <h2 class="text-center mb-5">My Projects</h2>
	    <div class="row g-4">

	       <!-- Project Card: E-commerce App -->
	       <div class="col-md-4">
	       	<a href="http://zuitt-bootcamp-prod-582-9211-lavaro.s3-website.us-east-1.amazonaws.com/" target="_blank">
	         <div class="project-card">
	           <img src="/images/ZariZari.png" alt="E-commerce App">
	           <div class="project-content">
	             <h3>E-commerce App</h3>
	             <p class="short-desc">Sample online shopping app.</p>
	             <p class="long-desc">A demo e-commerce application with product listings, shopping cart, and secure checkout flow. Designed to showcase frontend and backend integration.</p>
	           </div>
	         </div>
	    	   </a>
	       </div>

	      <!-- Project Card: Wuxia-Themed E-Commerce -->
	      <div class="col-md-4">
	      	<a href="https://home-page-exam-mu.vercel.app/" target="_blank">
	        <div class="project-card">
	          <img src="/images/Wuxia.png" alt="Wuxia-Themed E-Commerce">
	          <div class="project-content">
	            <h3>Wuxia E-Commerce</h3>
	            <p class="short-desc">Static wuxia-themed online store.</p>
	            <p class="long-desc">
	              Created a visually immersive static e-commerce website using HTML, CSS, and Bootstrap. Focused on product display, responsive layout, and user navigation, inspired by wuxia aesthetics to enhance engagement.
	            </p>
	          </div>
	        </div>
	      	</a>
	      </div>

	      <!-- Project Card: Course Booking -->
	      <div class="col-md-4">
	      	<a href="https://course-booking-roan.vercel.app/" target="_blank">
	        <div class="project-card">
	          <img src="/images/CourseBooking.png" alt="Course Booking App">
	          <div class="project-content">
	            <h3>Course Booking App</h3>
	            <p class="short-desc">Web app for booking online courses.</p>
	            <p class="long-desc">An intuitive booking system where users can browse, enroll, and manage online courses. Built with a responsive UI and secure backend APIs.</p>
	          </div>
	        </div>
	       </a>
	      </div>

	      <!-- Project Card: Movie Catalog App -->
	      <div class="col-md-4">
	      	<a href="https://movie-app-eight-gules.vercel.app/" target="_blank">
	        <div class="project-card">
	          <img src="/images/MovieApp.png" alt="Movie Catalog Application">
	          <div class="project-content">
	            <h3>Movie Catalog Application</h3>
	            <p class="short-desc">Full-stack movie search and watchlist app.</p>
	            <p class="long-desc">
	              Developed a MEVN stack application with Node/Express and MongoDB backend, and Vue.js + Bootstrap frontend. Integrated external movie APIs allowing users to search, browse, and save favorite movies. Implemented user authentication and personalized watchlists.
	            </p>
	          </div>
	        </div>
	      	</a>
	      </div>

	      <!-- Project Card: Quackr Blog App -->
	      <div class="col-md-4">
	        <a href="https://blog-client-eosin-rho.vercel.app/" target="_blank">
	          <div class="project-card">
	            <img src="/images/BlogApp.png" alt="Quackr Blog App">
	            <div class="project-content">
	              <h3>Quackr Blog</h3>
	              <p class="short-desc">A simple blogging platform.</p>
	              <p class="long-desc">
	                Full-stack MEVN blog application where users can create, read, update, and delete posts. 
	                Built with Node.js, Express, and MongoDB for the backend, and Vue.js with Bootstrap for a clean and responsive UI. 
	                Features include user authentication, post management, and comment functionality.
	              </p>
	            </div>
	          </div>
	        </a>
	      </div>

	      <!-- Project Card: Fitness Tracker -->
	      <div class="col-md-4">
	      	<a href="https://fitness-app-xi-pearl.vercel.app/" target="_blank">
	        <div class="project-card">
	          <img src="/images/FitnessTracker.png" alt="Fitness Tracker App">
	          <div class="project-content">
	            <h3>Fitness Tracker</h3>
	            <p class="short-desc">Track workouts and monitor progress.</p>
	            <p class="long-desc">
	              Full-stack MEVN application for logging and tracking workouts. Backend RESTful API built with Node/Express and MongoDB to store workout data. Vue.js frontend with Bootstrap provides real-time statistics, progress tracking, and an intuitive user interface.
	            </p>
	          </div>
	        </div>
	      	</a>
	      </div>

	      <!-- Project Card: Job Tracker -->
	      <div class="col-md-4">
	      	<a href="https://job-tracker-client-gold.vercel.app/" target="_blank">
	        <div class="project-card">
	          <img src="/images/JobTracker.png" alt="Job Tracker App">
	          <div class="project-content">
	            <h3>Job Tracker</h3>
	            <p class="short-desc">Manage job applications efficiently.</p>
	            <p class="long-desc">
	              MEVN stack application for tracking job applications. Backend API with Node/Express and MongoDB stores job posts, application statuses, and deadlines. Vue.js + Bootstrap frontend features job filtering, status updates, and user-friendly navigation.
	            </p>
	          </div>
	        </div>
	      	</a>
	      </div>

	    </div>
	  </div>
	</section>
</template>


<script setup>
	// computed function from Vue to define reactive derived state.
	import {computed} from 'vue';
	// card that will be reused
	import ProjectCard from './ProjectCard.vue';

	// data
	import projects from '../data/projects.json'

	// This will be used to define the number of cards per row.
	const chunkSize = 3;

	// Create a computed property that splits the projects into smaller arrays ("chunks")
	// Each chunk will contain up to the number of the 'chunkSize' number of projects.
	//This allows us to group them visually in separate rows in the UI.
	const chunkedProjects = computed(() => {
		const chunks = [];

		for( let i = 0; i < projects.length; i += chunkSize){
			chunks.push(projects.slice(i, i + chunkSize));
		}

		return chunks;
	})

</script>

<style scoped>
	#projects {
	    background-color: white !important;
	}

	#projects h2 {
	    font-weight: 700;
	    color: #dc8696; /* deep navy title */
	    text-align: center;
	    margin-bottom: 2.5rem;
	}

	/* Fade-in and slide-up animation */
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

	/* Project Card */
	.project-card {
	    background: #fff;
	    border-radius: 12px;
	    overflow: hidden;
	    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
	    transition: transform 0.3s ease, box-shadow 0.3s ease, opacity 0.5s ease;
	    cursor: pointer;

	    opacity: 0;              /* start hidden */
	    transform: translateY(20px);
	    animation: fadeInUp 0.6s ease forwards;
	}

	/* Stagger animation for cards */
	.row .col-md-4:nth-child(1) .project-card { animation-delay: 0.1s; }
	.row .col-md-4:nth-child(2) .project-card { animation-delay: 0.2s; }
	.row .col-md-4:nth-child(3) .project-card { animation-delay: 0.3s; }
	.row .col-md-4:nth-child(4) .project-card { animation-delay: 0.4s; }
	.row .col-md-4:nth-child(5) .project-card { animation-delay: 0.5s; }
	.row .col-md-4:nth-child(6) .project-card { animation-delay: 0.6s; }
	.row .col-md-4:nth-child(7) .project-card { animation-delay: 0.7s; }
	.row .col-md-4:nth-child(8) .project-card { animation-delay: 0.8s; }

	/* Hover effect: lift + scale + shadow */
	.project-card:hover {
	    transform: translateY(-8px) scale(1.02);
	    box-shadow: 0 12px 24px rgba(0,0,0,0.2);
	}

	/* Image inside card */
	.project-card img {
	    width: 100%;
	    height: 200px;
	    object-fit: cover;
	    transition: transform 0.4s ease;
	}

	/* Image zoom on hover */
	.project-card:hover img {
	    transform: scale(1.05);
	}

	/* Card content */
	.project-content {
	    padding: 1rem;
	}

	/* Titles */
	.project-content h3 {
	    font-size: 1.25rem;
	    font-weight: 600;
	    color: #b8789a;
	    margin-bottom: 0.5rem;
	}

	/* Descriptions */
	.project-content p {
	    margin: 0;
	    font-size: 0.95rem;
	    color: #32353a;
	    font-family: "Poppins", sans-serif;
	    font-weight: 300;
	    font-style: normal;
	}

	/* Short vs Long Descriptions */
	.short-desc,
	.long-desc {
	    overflow: hidden;
	    transition: all 0.4s ease;
	}

	/* Short description visible by default */
	.short-desc {
	    opacity: 1;
	    max-height: 100px;
	}

	/* Long description hidden by default */
	.long-desc {
	    opacity: 0;
	    max-height: 0;
	    margin-top: 0;
	}

	/* Swap descriptions on hover */
	.project-card:hover .short-desc {
	    opacity: 0;
	    max-height: 0;
	    margin: 0;
	}

	.project-card:hover .long-desc {
	    opacity: 1;
	    max-height: 300px; /* allow space for full text */
	    margin-top: 0.5rem;
	}

</style>