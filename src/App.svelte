<!-- App.svelte -->
<script>
	let slogan = "One Block at a Time";
	let tagline = "Turning our Vision into Reality is what we wish to accomplish.";
	let email = '';
  import Fa from 'svelte-fa'
  import { faEnvelope, faFlag, faMailBulk, faMailReply } from '@fortawesome/free-solid-svg-icons'
  import { faGithub, faInstagram, faLinkedin } from '@fortawesome/free-brands-svg-icons';
  async function subscribe() {
    if (email) {
      const response = await fetch('/subscribe', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({ email }),
      });

      if (response.ok) {
        alert('Subscription successful! You will receive updates via email.');
        email = '';
      } else {
        alert('Subscription failed. Please try again later.');
      }
    }
  }
  </script>
  
  <style>
	.cname {
	  font-size: 80px;
	  color: #ffffff;
	  text-align: center;
	  font-family: 'Cormorant Garamond', serif;
	  font-weight: bold;
	}
  
	.navbar {
	  background: #000000;
	  margin: 0px;
	  padding: 20px;
	  position: fixed;
	  top: 0;
	  left: 0;
	  right: 0;
	  z-index: 1000;
	  width: 100%;
	}
  
	/* Add styles for the section below the navbar */
	.section {
	  margin-top: 20px; /* Adjust the margin-top to leave space below the fixed navbar */
	  flex-direction: row;
	  padding: 20px;
	  display: flex;
	  justify-content: center; /* Center horizontally */
	  align-items: center; /* Center vertically */
	}
  
	.left-column {
	  width: 50%; /* Divide into two columns (6/6) */
	  padding: 20px;
	  margin-top: 50px;
	}
  
	.right-column {
	  width: 50%;
	  padding: 20px;
	  margin-top: 50px;
	}
  
	.image {
	  max-width: 100%; /* Ensure the image fits within the column */
	  height: auto;
	  display: block;
	  margin: 0 auto; /* Center the image horizontally */
	}
  
	.slogan {
	  font-size: 70px;
	  color: #000000;
	  text-align: center;
	  font-family: 'Poppins', serif;
	  font-weight: 900;
	  line-height: 1;
	}
  
	.tagline {
	  font-size: 24px;
	  margin-top: 10px;
	  color: #000000;
	  text-align: center;
	  font-family: 'Poppins', serif;
	  font-weight: 400;
	  line-height: 1;
	}
	
	.who {
	  font-size: 70px;
	  color: #000000;
	  text-align: center;
	  font-family: 'Poppins', serif;
	  font-weight: 900;
	  line-height: 1;
	}

	.whot {
	  font-size: 40px;
	  color: #000000;
	  text-align: center;
	  font-family: 'Poppins', serif;
	  font-weight: 900;
	  line-height: 1;
	}

	.who1 {
	  font-size: 24px;
	  margin-top: 10px;
	  color: #000000;
	  text-align: center;
	  font-family: 'Poppins', serif;
	  font-weight: 400;
	  line-height: 1;
	}
	
.card {
  position: relative;
  z-index: 1;
  display: grid;
  place-content: center;
  width: 100%;
  height: 400px;
  color: #000;
  text-align: center;
  background: url('/image/bd.png') center no-repeat;
  background-size: cover;
  padding: 10px;
  border-radius: 0px;
  overflow: hidden;
}
.card::before,
.card::after {
  content: '';
  position: absolute;
  left: 0;
  z-index: -1;
  width: 450px;
  height: calc(60% + 40px);
  background-color: #fff;
  transition: transform 0.5s 0.25s;
}
.card::before {
  top: 0;
  clip-path: polygon(0 0, 100% 0, 100% 45%, 0% 100%);
  transform: translateY(-100%);
}
.card::after {
  bottom: 0;
  clip-path: polygon(0 55%, 100% 0, 100% 100%, 0% 100%);
  transform: translateY(100%);
}

.card__body {
  opacity: 0;
  transition: opacity 0.25s;
}
.card__title {
  color: #0F044C;
  margin-bottom: 15px;
}
.card:hover::before,
.card:hover::after {
  transform: translateY(0);
}
.card:hover .card__body {
  opacity: 1;
  transition-delay: 0.75s;
}

.card1 {
  position: relative;
  z-index: 1;
  display: grid;
  place-content: center;
  width: 100%;
  height: 400px;
  color: #000;
  text-align: center;
  background: url('/image/da.png') center no-repeat;
  background-size: cover;
  padding: 10px;
  border-radius: 0px;
  overflow: hidden;
}
.card1::before,
.card1::after {
  content: '';
  position: absolute;
  left: 0;
  z-index: -1;
  width: 450px;
  height: calc(60% + 40px);
  background-color: #fff;
  transition: transform 0.5s 0.25s;
}
.card1::before {
  top: 0;
  clip-path: polygon(0 0, 100% 0, 100% 45%, 0% 100%);
  transform: translateY(-100%);
}
.card1::after {
  bottom: 0;
  clip-path: polygon(0 55%, 100% 0, 100% 100%, 0% 100%);
  transform: translateY(100%);
}

.card1:hover::before,
.card1:hover::after {
  transform: translateY(0);
}
.card1:hover .card__body {
  opacity: 1;
  transition-delay: 0.75s;
}

.card2 {
  position: relative;
  z-index: 1;
  display: grid;
  place-content: center;
  width: 100%;
  height: 400px;
  color: #000;
  text-align: center;
  background: url('/image/scd.png') center no-repeat;
  background-size: cover;
  padding: 10px;
  border-radius: 0px;
  overflow: hidden;
}
.card2::before,
.card2::after {
  content: '';
  position: absolute;
  left: 0;
  z-index: -1;
  width: 450px;
  height: calc(60% + 40px);
  background-color: #fff;
  transition: transform 0.5s 0.25s;
}
.card2::before {
  top: 0;
  clip-path: polygon(0 0, 100% 0, 100% 45%, 0% 100%);
  transform: translateY(-100%);
}
.card2::after {
  bottom: 0;
  clip-path: polygon(0 55%, 100% 0, 100% 100%, 0% 100%);
  transform: translateY(100%);
}

.card2:hover::before,
.card2:hover::after {
  transform: translateY(0);
}
.card2:hover .card__body {
  opacity: 1;
  transition-delay: 0.75s;
}

.card3 {
  position: relative;
  z-index: 1;
  display: grid;
  place-content: center;
  width: 100%;
  height: 400px;
  color: #000;
  text-align: center;
  background: url('/image/bs.png') center no-repeat;
  background-size: cover;
  padding: 10px;
  border-radius: 0px;
  overflow: hidden;
}
.card3::before,
.card3::after {
  content: '';
  position: absolute;
  left: 0;
  z-index: -1;
  width: 450px;
  height: calc(60% + 40px);
  background-color: #fff;
  transition: transform 0.5s 0.25s;
}
.card3::before {
  top: 0;
  clip-path: polygon(0 0, 100% 0, 100% 45%, 0% 100%);
  transform: translateY(-100%);
}
.card3::after {
  bottom: 0;
  clip-path: polygon(0 55%, 100% 0, 100% 100%, 0% 100%);
  transform: translateY(100%);
}

.card3:hover::before,
.card3:hover::after {
  transform: translateY(0);
}
.card3:hover .card__body {
  opacity: 1;
  transition-delay: 0.75s;
}

.card4 {
  position: relative;
  z-index: 1;
  display: grid;
  place-content: center;
  width: 100%;
  height: 400px;
  color: #000;
  text-align: center;
  background: url('/image/c.png') center no-repeat;
  background-size: cover;
  padding: 10px;
  border-radius: 0px;
  overflow: hidden;
}
.card4::before,
.card4::after {
  content: '';
  position: absolute;
  left: 0;
  z-index: -1;
  width: calc(100% + 5px);
  height: calc(60% + 40px);
  background-color: #fff;
  transition: transform 0.5s 0.25s;
}
.card4::before {
  top: 0;
  clip-path: polygon(0 0, 100% 0, 100% 45%, 0% 100%);
  transform: translateY(-100%);
}
.card4::after {
  bottom: 0;
  clip-path: polygon(0 55%, 100% 0, 100% 100%, 0% 100%);
  transform: translateY(100%);
}

.card4:hover::before,
.card4:hover::after {
  transform: translateY(0);
}
.card4:hover .card__body {
  opacity: 1;
  transition-delay: 0.75s;
}

.oe{
	margin-bottom: 0px;
	padding: 0;
	font-size: 70px;
	  color: #000000;
	  text-align: center;
	  font-family: 'Poppins', serif;
	  font-weight: 900;
	  line-height: 1;
}
.left-column1 {
	  width: 25%; /* Divide into two columns (6/6) */
	  padding: 20px;
	  margin: 0;
	  align-content: center;
	  margin-top: 50px;
	}
.left-column2 {
	  width: 25%; /* Divide into two columns (6/6) */
	  padding: 20px;
	  margin: 0;
	  align-content: center;
	  margin-top: 50px;
	}
  
.right-column1 {
	  width: 25%;
	  padding: 20px;
	  margin: 0;
	  align-content: center;
	  margin-top: 50px;
	}
.right-column2 {
	  width: 25%;
	  padding: 20px;
	  margin: 0;
	  align-content: center;
	  margin-top: 50px;
	}
.section1 {
	  margin-top: 0px; /* Adjust the margin-top to leave space below the fixed navbar */
	  flex-direction: row;
	  padding: 20px;
	  display: flex;
	  justify-content: center; /* Center horizontally */
	  align-items: center; /* Center vertically */
	}

  
	/* Responsive styles for smaller screens */
	@media (max-width: 768px) {
	  .section {
		flex-direction: column; /* Stack columns on smaller screens */
		align-items: center; /* Center content vertically */
		margin-top: 60px; /* Adjust margin for smaller screens */
	  }
  
	  .left-column {
		width: 100%; /* Full width on smaller screens */
		text-align: center;
	  }
  
	  .right-column {
		width: 100%;
		margin-top: 20px; /* Reduce margin for smaller screens */
	  }
	}
	@media (max-width: 768px) {
    .section {
      flex-direction: column; /* Stack columns on smaller screens */
      align-items: center; /* Center content vertically */
      margin-top: 60px; /* Adjust margin for smaller screens */
    }

    .left-column,
    .right-column {
      width: 100%; /* Full width on smaller screens */
      text-align: center;
    }

    .right-column {
      margin-top: 20px; /* Reduce margin for smaller screens */
    }

    .section1 {
      flex-direction: column; /* Stack cards on smaller screens */
      align-items: center;
    }

    .left-column1,
    .left-column2,
    .right-column1,
    .right-column2 {
      width: 100%; /* Full width for cards on smaller screens */
      margin: 0;
      text-align: center;
      margin-bottom: 20px;
    }
  }
  /* Mobile View */
  @media screen and (max-width: 480px) {
    .cname {
      font-size: 40px; /* Reduce the logo font size */
    }

    .navbar {
      padding: 10px; /* Reduce navbar padding */
    }

    .section {
      margin-top: 20px; /* Adjust spacing between sections */
    }

    .slogan {
      font-size: 36px; /* Reduce font size for slogans */
    }

    .tagline {
      font-size: 18px; /* Reduce font size for tagline */
      margin-top: 5px; /* Adjust spacing for tagline */
    }

    .who,
    .oe {
      font-size: 36px; /* Reduce font size for headings */
    }

    .whot {
      font-size: 24px; /* Reduce font size for subheadings */
    }

    .who1 {
      font-size: 16px; /* Reduce font size for content */
    }

    .card,
    .card1,
    .card2,
    .card3,
	.card4{
      height: 300px; /* Reduce card height */
    }

    .card::before,
    .card::after,
    .card1::before,
    .card1::after,
    .card2::before,
    .card2::after,
    .card3::before,
    .card3::after,
	.card4::before,
    .card4::after{
      width: 400px; /* Reduce card pseudo-element width */
      height: calc(60% + 40px); /* Adjust card pseudo-element height */
    }
  }
  
  .footer{
    padding-top: 20px;
    background-color: #000;
  }
  </style>
  
  <div>
  <nav class="navbar">
	<h1 class="cname">QuidStack</h1>
  </nav>
  
  <div class="section">
	<div class="left-column">
	  <h1 class="slogan">One Block at a Time</h1>
	  <h2 class="tagline">Turning our Vision into Reality is what we wish to accomplish.</h2>
	</div>
	<div class="right-column">
	  <img class="image" src="QSLogo.png" alt="QuidStack Office Building" />
	</div>
  </div>
  <div class="section">
	<div class="left-column">
	  <img class="image" src="image/pattern.png" alt="QuidStack Office Building" />
	</div>
	<div class="right-column">
		<h1 class="who">Who We Are</h1>
	  <h2 class="who1">At Quid Stack, we're not constrained by tradition.we are committed to mastering the art of full-stack blockchain software development. With a deep understanding of blockchain technology, we create innovative solutions that tackle complex challenges head-on.</h2>
	</div>
  </div>
  <div class="section">
	<div class="left-column">
	  <h1 class="slogan">What We Do</h1>
	  <h2 class="who1">Despite being freshers in the field of blockchain technology, we are driven by a clear mission: to provide innovative and tailored solutions that harness the potential of blockchain for our clients.</h2>
	</div>
	<div class="right-column">
	  <img class="image" src="image/pattern1.png" alt="QuidStack Office Building" />
	</div>
  </div>
  <div style="margin-top: 100px;">
	<h1 class="oe">OurExperties</h1>
  </div>
  <div class="section1">
	<div class="left-column1">
		<article class="card" style="margin-bottom: 20px;">
			<div class="card__body">
				<h2 class="card__title whot">Blockchain<br>Development</h2>
				<p class="who1">
					Our core expertise lies in developing robust, secure, and scalable blockchain solutions.
				</p>
			</div>
		</article>
	</div>
	<div class="right-column1">
		<article class="card1" style="margin-bottom: 20px;">
			<div class="card__body">
				<h2 class="card__title whot">Decentralized<br>Applications(DApps)</h2>
				<p class="who1">
					DApps that leverage blockchain technology to enhance transparency, security, and efficiency.
				</p>
			</div>
		</article>
	</div>
	<div class="left-column2">
		<article class="card2" style="margin-bottom: 20px;">
			<div class="card__body">
				<h2 class="card__title whot">Smart Contract<br>Development</h2>
				<p class="who1">
					Smart contracts are at the heart of blockchain applications.
				</p>
			</div>
		</article>
	</div>
	<div class="right-column2">
		<article class="card3" style="margin-bottom: 20px;">
			<div class="card__body">
				<h2 class="card__title whot">Blockchain<br>Security</h2>
				<p class="who1">
					Security is paramount in the blockchain space. We are developing our own security algorithms.
				</p>
			</div>
		</article>
	</div>
  </div>

  <div style="margin-top: 200px;">
	<h1 class="oe">Comming Soon!</h1>
  </div>
  <div class="section">
	<div class="left-column">
		<article class="card4" style="margin-bottom: 20px;">
			<div class="card__body">
				<img class="image" src="image/VoizNotch.png" alt="QuidStack Office Building" />
			</div>
		</article>
	</div>
  </div> 
</div>
<div>
  <!-- Your existing HTML content here -->

<footer class="footer">
  <div class="container" style="text-align: center;">
    <div class="footer-links">
      <a href="https://github.com/QuidStack/QuidStack.git" target="_blank" class="social-link" style="margin-left: 10px; margin-right: 10px">
        <Fa
          icon={faGithub}
          class="bg-gold"
          size="4x"
          color="#4078c0"
        />
      </a>
      <a href="https://www.linkedin.com/company/96399629/admin/feed/posts/" target="_blank" class="social-link" style="margin-left: 10px; margin-right: 10px">
        <Fa
          icon={faLinkedin}
          class="bg-gold"
          size="4x"
          color="#0072b1"
        />
      </a>
      <a href="mailto:emailquidstack@gmail.com" target="_blank" class="social-link" style="margin-left: 10px; margin-right: 10px">
        <Fa
          icon={faEnvelope}
          class="bg-gold"
          size="4x"
          color="#C71610"
        />
      </a>
    <div class="copyright who1" style="text-align: center; padding-bottom:20px; color:#fff;">
      <!-- svelte-ignore a11y-missing-attribute -->
      &copy; 2023 <a style="font-family: 'Cormorant Garamond', serif; font-size:30px;">QuidStack</a>. All Rights Reserved.
    </div>
  </div>
</footer>

</div>