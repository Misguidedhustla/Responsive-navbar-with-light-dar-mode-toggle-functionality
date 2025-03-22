# Responsive-navbar-with-light-dar-mode-toggle-functionality
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="description" content="Responsive Navbar with Dark Mode using HTML, CSS and JavaScript">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Navbar with Dark Mode</title>
  <link rel="icon" href="WEBZEN.png" type="image/png">
  <link rel="stylesheet" href="nav.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css" crossorigin="anonymous" referrerpolicy="no-referrer" />
</head>
<body>
  <nav class="navbar">
    <div class="nav-left">
      <div class="logo">
        <img src="webzen.png" alt="WEBZEN Logo" id="logoImage">
      </div>
    </div>
      <button id="darkModeToggle">
        <i class="fas fa-moon"></i><span id="modeText">Nox</span>
      </button>
    

    <div class="menuicon" id="menuIcon">
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </div>
    
    <ul class="navlinks" id="navLinks">
      <li><a class="scale" href="#"><i class="fas fa-home"></i> Home</a></li>
      <li><a class="scale" href="#"><i class="fas fa-info-circle"></i> About Us</a></li>
      <li><a class="scale" href="#"><i class="fas fa-concierge-bell"></i> Services</a></li>
      <li><a class="scale" href="#"><i class="fas fa-blog"></i> Blog</a></li>
      <li><a class="scale" href="#"><i class="fas fa-question-circle"></i> FAQs</a></li>
    </ul>
  </nav>

  <div class="form-box">
    <div class="flip-box">
      <!-- Login Form -->
      <div class="form-container login">
        <h2>Login</h2>
        <form id="loginForm">
          <div class="input-box">
            <input type="text" id="loginUsername" placeholder=" " required>
            <label for="loginUsername">Username</label>
            <i class="fa fa-user"></i>
          </div>

          <div class="input-box">
            <input type="password" id="loginPassword" placeholder=" " required>
            <label for="loginPassword">Password</label>
            <i class="fa fa-lock"></i>
          </div>

          <button type="submit" id="loginButton">Login</button>
          <p><a href="#">Forgot password?</a></p>
          <p>Don't have an account? <span id="flipToSignup">Sign up</span></p>
        </form>
      </div>

      <!-- Signup Form -->
      <div class="form-container signup">
        <h2>Sign Up</h2>
        <form id="signupForm">
          <div class="input-box">
            <input type="text" id="signupName" placeholder=" " required>
            <label for="signupName">Full Name</label>
            <i class="fa fa-user"></i>
          </div>

          <div class="input-box">
            <input type="email" id="signupEmail" placeholder=" " required>
            <label for="signupEmail">Email</label>
            <i class="fa fa-envelope"></i>
          </div>

          <div class="input-box">
            <input type="password" id="signupPassword" placeholder=" " required>
            <label for="signupPassword">Password</label>
            <i class="fa fa-lock"></i>
          </div>

          <button type="submit" id="">Sign Up</button>
          <p>Already have an account? <span id="flipToLogin">Login</span></p>
        </form>
      </div>
    </div>
  </div>

  <script src="nav.js" async></script>
</body>
</html>


* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Times New Roman', Times, serif;
  background-color: rgb(194, 198, 199);
  align-items: center;
  justify-content: center;
  height: 100vh;
  color:#007BFF;
  transition: background 0.5s ease-in-out, color 0.5s ease-in-out;
}

/* Dark Mode Styles */
body.dark-mode {
  background-color: #161616;
  color: #f8f8f8;
}

.dark-mode .navbar {
  background-color: #121212;
  color: #c4eb18;
}

.dark-mode .navlinks a {
  color: #c4eb18;
}

.navbar {
  display: flex;
  justify-content: space-between; /* Space between logo and nav items */
  align-items: center;
  padding: 10px 30px; /* Adjust padding for more space */
  background: #f8f8f8ce;
  letter-spacing: 1.5px;
  color: #007BFF;
  transition: background 0.5s ease-in-out, color 0.5s ease-in-out;
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  z-index: 200;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1); /* Optional: Add a shadow for better visibility */
}

/* Group logo and dark mode toggle */
.nav-left {
  display: flex;
  align-items: center;
  gap: 15px; /* Add spacing between logo and other items */
}

.logo {
  display: flex;
  align-items: center;
  justify-content: center;
  max-width: 150px; /* Set a maximum width for the logo */
  height: auto; /* Maintain aspect ratio */
  margin: 0 10px; /* Add some spacing around the logo */
}

.logo img {
  width: 120%; /* Increase size while keeping it responsive */
  height: auto; /* Maintain aspect ratio */
  object-fit: contain; /* Ensure the image fits within the container */
  transition: transform 0.3s ease-in-out, filter 0.3s ease-in-out;
  filter: brightness(1.4); /* Increase brightness for better visibility */
}

.logo img:hover {
  transform: scale(1.2) rotate(3deg); /* Slightly larger hover effect */
  filter: brightness(1.6); /* Further enhance brightness on hover */
}

#codeicon {
  font-size: 35px;
  padding: 4px;
  cursor: help;
}

/* Dark Mode Toggle */
#darkModeToggle {
  background: none;
  border: none;
  color: #007BFF;
  font-size: 20px;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 5px;
  transition: transform 0.5s ease-in-out;
}

#darkModeToggle:hover {
  transform: none; /* Prevent animation when the parent is hovered */
}

#darkModeToggle #modeText:hover,
#darkModeToggle i:hover {
  transform: scale(1.2) rotate(-10deg); /* Add scale and rotation animation */
  transition: transform 0.3s ease-in-out;
}

.dark-mode #darkModeToggle {
  color: #c4eb18;
}

.dark-mode #darkModeToggle #modeText:hover,
.dark-mode #darkModeToggle i:hover {
  transform: scale(1.2) rotate(10deg); /* Add scale and rotation animation for dark mode */
  transition: transform 0.3s ease-in-out;
}

/* Navbar Links */
.navlinks {
  list-style: none;
  display: flex;
  gap: 20px; /* Adjust spacing between menu items */
  padding: 0;
  margin: 0;
  align-items: center; /* Align items vertically */
  white-space: nowrap; /* Prevent items from wrapping to the next line */
}

.navlinks a {
  text-decoration: none;
  font-size: 16px; /* Adjust font size */
  color: #007BFF;
  transition: transform 0.5s ease, padding 0.5s ease, color 0.5s ease-in-out;
  position: relative;
  display: inline-block;
  padding: 5px 10px; /* Add padding for better spacing */
}

.navlinks a::before {
  content: '';
  position: absolute;
  width: 100%;
  height: 1px;
  bottom: 0;
  left: 0;
  background-color: #007BFF;
  visibility: hidden;
  transform: scaleX(0);
  transition: all 0.5s ease-in-out;
}

.navlinks a:hover::before {
  visibility: visible;
  transform: scaleX(1);
}

.dark-mode .navlinks a::before {
  background-color: #f8f8f8ce;
}


/* Dark Mode Navbar Links */
.dark-mode .navlinks a {
  color: #c4eb18;
}

/* Hover Effects */
.navlinks a:hover {
  transform: translateY(-5px) scale(1.1);
  letter-spacing: 2px;
}

.navlinks a:hover i {
  transform: rotate(360deg);
  transition: transform 0.7s ease-in-out;
}

.menuicon {
  display: none; /* Hide hamburger icon on larger screens */
  flex-direction: column;
  cursor: pointer;
  position: absolute;
  right: 20px;
  top: 15px;
  z-index: 20;
}

.menuicon .bar {
  display: block;
  width: 30px;
  height: 3px;
  margin: 5px auto;
  background-color: #007BFF;
  transition: 0.4s;
}

.dark-mode .menuicon .bar {
  background-color: #c4eb18;
}

.form-box {
  width: 350px;
  height: 450px;
  position: fixed; /* Changed from absolute to fixed for consistent centering */
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%); /* Centers it perfectly */
  display: flex;
  justify-content: center;
  align-items: center;
  background: transparent; /* Set background to transparent */
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
  z-index: 100; /* Ensures it stays above other elements */
}

/* Ensure the form stays centered even on smaller screens */
@media (max-width: 768px) {
  .form-box {
    width: 90%;
    padding: 15px; /* Adjust padding for smaller screens */
    border: none; /* Remove border to prevent overflow */
    top: 55%; /* Move the form box slightly lower */
    left: 50%;
    transform: translate(-50%, -50%);
    animation: fade-in 1s ease-in-out; /* Smooth fade-in animation */
  }

  @keyframes fade-in {
    0% {
      opacity: 0;
      transform: translate(-50%, -60%);
    }
    100% {
      opacity: 1;
      transform: translate(-50%, -50%);
    }
  }

  .form-container {
    text-shadow: none; /* Ensure text is not blurred */
    transform: none; /* Remove scaling effects that might cause blurriness */
  }
}

.flip-box {
  width: 100%;
  height: 100%;
  position: absolute;
  transition: transform 0.8s ease-in-out, background-color 0.8s ease-in-out;
  transform-style: preserve-3d;
}

.form-container {
  width: 100%;
  height: 100%;
  position: absolute;
  background: white;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  backface-visibility: hidden;
  border-radius: 10px;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
}

.signup {
  transform: rotateY(180deg);
}

.flip-active {
  transform: rotateY(180deg);
}

.flip-active .form-box {
  background: black; /* Set background to black during flip */
}

.flip-active .flip-box {
  background-color: black; /* Set background to black during flip */
}

h2 {
  margin-bottom: 20px;
}

.input-box {
  position: relative;
  width: 100%;
  margin: 15px 0;
}

.input-box input {
  width: 100%;
  padding: 10px 35px 10px 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  outline: none;
  font-size: 16px;
  transition: 0.3s;
}

.input-box input:focus {
  border-color: #007BFF;
  border-radius: 2px;
}

.dark-mode .input-box input{
  background: #121212;
  color:#777;
}

.dark-mode .input-box input:focus {
  border-color: #c4eb18;
  border-radius: 2px;
}

.input-box label {
  position: absolute;
  left: 10px;
  top: 50%;
  transform: translateY(-50%);
  color: #777; /* Default label color */
  transition: 0.3s ease-in-out;
  font-size: 16px;
  pointer-events: none;
}

.input-box input:focus + label,
.input-box input:not(:placeholder-shown) + label {
  top: 3px;
  left: 10px;
  font-size: 12px;
  color: #007BFF;
}

.dark-mode .input-box input:focus + label,
.dark-mode .input-box input:not(:placeholder-shown) + label {
  color: #c4eb18;
}

.input-box i {
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
  color: #777;
  transition: 0.3s;
}

.input-box input:focus + label + i {
  color: #007BFF;
}

.dark-mode .input-box input:focus + label + i{
  color: #c4eb18;
}

button {
  width: 100%;
  padding: 10px;
  background: #007BFF;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  margin-top: 10px;
  font-size: 16px;
  position: relative; /* Required for the arrow animation */
  overflow: hidden; /* Prevents the arrow from overflowing */
  transition: background 0.3s ease-in-out, transform 0.3s ease-in-out;
}

button::after {
  content: '»';/* Forward arrow */
  position: absolute;
  right: -20px; /* Start outside the button */
  top: 50%;
  transform: translateY(-50%);
  font-size: 18px;
  color: white;
  transition: right 0.5s ease-in-out;
}

button:hover {
  background: #0056b3;
  transform: scale(1.05); /* Slightly enlarge the button */
}

button:hover::after {
  right: 50px; /* Move the arrow inside the button */
}

.dark-mode button {
  background: #c4eb18;
  color: #121212;
}

.dark-mode button:hover {
  background: #88a701;
}

.dark-mode button::after {
  color: #121212;
}

p {
  margin: 10px 0;
}

p a {
  color: #007BFF;
  text-decoration: none;
}

p span {
  color: #007BFF;
  cursor: pointer;
  font-weight: bold;
}

p span:hover {
  text-decoration: underline;
}



.dark-mode .form-container {
  background: #161616;
  color: #c4eb18;
}

.signup {
  transform: rotateY(180deg);
}

.flip-active {
  transform: rotateY(180deg);
}

/* Ensuring Full Mobile Responsiveness */
@media (max-width: 768px) {
  .form-box {
    width: 90%;
    max-width: 350px;
  }
}

.dark-mode .form-container {
  background:#161616 ;
  color: #c4eb18;
}

.signup {
  transform: rotateY(180deg);
}

/* Flip Animation */
.flip-active {
  transform: rotateY(180deg);
}

/* Input Fields */
input {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 5px;
  outline: none;
}

p a {
  color: #0056b3;
  text-decoration: none;
}

.dark-mode p a {
  color: #c4eb18;
}

/* Button */
button {
  width: 100%;
  padding: 10px;
  background: #007BFF;
  font-family: 'Times New Roman', Times, serif;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  margin-top: 10px;
  font-size: 16px;
}

.dark-mode button {
  background: #c4eb18;
  color: #121212;
  font-family: 'Times New Roman', Times, serif;
}

.dark-mode button:hover {
  background: #88a701;
}

button:hover {
  background: #0056b3;
}

/* Flip Links */
p {
  margin: 10px 0;
}

p span {
  color: #007BFF;
  cursor: pointer;
  font-weight: bold;
}

p span:hover {
  text-decoration: underline;
}

/* Social Login */
.social-login {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 10px;
}

.social-login button {
  display: flex;
  align-items: center;
  justify-content: center;
  background: #db4437;
  border: none;
  font-size: 14px;
}

.social-login .facebook {
  background: #1877f2;
}

social-login i {
  margin-right: 10px;
}

/* Ensure the back side is hidden properly */
.signup {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
}

/* Mobile Responsive */
@media (max-width: 768px) {
  .nav-left {
    align-items: start;
  }

  #darkModeToggle {
    font-size: 18px;
  }

  .navlinks {
    flex-direction: column;
    position: fixed;
    top: 0;
    right: -100%;
    width: 250px;
    height: 100%;
    padding: 50px 20px;
    backdrop-filter: blur(5px);
    background:#f8f8f8ce;
    box-shadow: -2px 0 5px rgba(0, 0, 0, 0.1);
    transition: right 0.5s ease-in-out;
    z-index: 10;
  }

  .dark-mode .navlinks {
    background: #121212;
    color: #c4eb18;
  }
  .navlinks.active {
    right: 0;
  }

  .menuicon {
    display: flex; /* Show hamburger icon on smaller screens */
  }

  .navlinks a {
    color: #007BFF;
    padding: 8px 0 ;
    font-size: 18px;
  }

  .menuicon.active .bar:nth-child(1) {
    transform: translateY(24px) rotate(45deg);
  }

  .menuicon.active .bar:nth-child(2) {
    opacity: 0;
  }

  .menuicon.active .bar:nth-child(3) {
    transform: translateY(-10px) rotate(-45deg);
  }
}


const menuIcon = document.getElementById('menuIcon');
const navLinks = document.getElementById('navLinks');
const darkModeToggle = document.getElementById('darkModeToggle');

// Toggle Menu
menuIcon.addEventListener('click', (e) => {
  navLinks.classList.toggle('active');
  menuIcon.classList.toggle('active');
  e.stopPropagation();
});

// Close Menu when clicking outside
document.addEventListener('click', (e) => {
  if (navLinks.classList.contains('active') && !navLinks.contains(e.target) && e.target !== menuIcon) {
    navLinks.classList.remove('active');
    menuIcon.classList.remove('active');
  }
});

document.querySelectorAll('.navlinks a').forEach(link => {
  link.addEventListener('click', () => {
    navLinks.classList.remove('active');
    menuIcon.classList.remove('active');
  });
});


navLinks.addEventListener('click', (e) => e.stopPropagation());

// Dark Mode Toggle
function toggleDarkMode() {
  document.body.classList.toggle('dark-mode');
  localStorage.setItem('darkMode', document.body.classList.contains('dark-mode'));

  darkModeToggle.innerHTML = document.body.classList.contains('dark-mode')
    ? '<i class="fas fa-sun"></i> <span id="modeText">Lumos</span>'
    : '<i class="fas fa-moon"></i> <span id="modeText">Nox</span>';
}

// Load Dark Mode Preference
if (localStorage.getItem('darkMode') === 'true') {
  document.body.classList.add('dark-mode');
  darkModeToggle.innerHTML = '<i class="fas fa-sun"></i> <span id="modeText">lumos</span>';
}

darkModeToggle.addEventListener('click', toggleDarkMode);

const flipBox = document.querySelector('.flip-box');
const flipToSignup = document.getElementById('flipToSignup');
const flipToLogin = document.getElementById('flipToLogin');

if (flipToSignup && flipToLogin) {
    flipToSignup.addEventListener('click', () => {
        flipBox.classList.add('flip-active');
    });

    flipToLogin.addEventListener('click', () => {
        flipBox.classList.remove('flip-active');
    });
}

// Form Submission Alerts
document.getElementById("loginForm").addEventListener("submit", function (e) {
    e.preventDefault();
    alert("Login Submitted!");
});

document.getElementById("signupForm").addEventListener("submit", function (e) {
    e.preventDefault();
    alert("Signup Submitted!");
});


document.getElementById("loginForm").addEventListener("submit", function (e) {
      e.preventDefault();
      alert("Login Submitted!");
    });

    document.getElementById("signupForm").addEventListener("submit", function (e) {
      e.preventDefault();
      alert("Signup Submitted!");
    });

    document.addEventListener('DOMContentLoaded', () => {
  const buttons = document.querySelectorAll('button');

  buttons.forEach((button) => {
    button.addEventListener('click', () => {
      // Add the animation class
      button.classList.add('animate-arrow');

      // Remove the animation class after the animation completes (e.g., 300ms)
      setTimeout(() => {
        button.classList.remove('animate-arrow');
      }, 300);
    });
  });
});
