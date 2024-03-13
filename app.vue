<template>
  <div class="background-container">
    <div class="main-container">
      <div class="logo-container">
        <img src="@/assets/logo-white.png" alt="Logo" class="logo" />
      </div>
      <div class="countdown-container">
        <p>PROMOTION <br> ENDS IN</p>
      </div>

      <div class="countdowntime-container">
        <div class="countdown-group">
          <p class="countdowntime-container-p1">27</p>
          <p class="countdowntime-container-p2">Days</p>
        </div>
        <div class="countdown-group">
          <p class="countdowntime-container-p1">:</p>
        </div>
        <div class="countdown-group">
          <p class="countdowntime-container-p1">23</p>
          <p class="countdowntime-container-p2">Hours</p>
        </div>
        <div class="countdown-group">
          <p class="countdowntime-container-p1">:</p>
        </div>
        <div class="countdown-group">
          <p class="countdowntime-container-p1">45</p>
          <p class="countdowntime-container-p2">Minutes</p>
        </div>
        <div class="countdown-group">
          <p class="countdowntime-container-p1">:</p>
        </div>
        <div class="countdown-group">
          <p class="countdowntime-container-p1">07</p>
          <p class="countdowntime-container-p2">Seconds</p>
        </div>
      </div>

      <div class="user-actions">
        <button @click="scrollToRegister" class="register-button">REGISTER NOW</button>
        <div v-if="isDropdownOpen || isPopupOpen" :class="{ 'dropdown': isDropdownOpen, 'user-dropdown': isPopupOpen }">
          <button v-if="isDropdownOpen" @click="showPopup">Login</button>
        </div>
        <img src="@/assets/people-icon.png" alt="User Icon" @click="openDropdown" class="user-icon" />
      </div>
       
      <!-- Popup for Login -->
      <div v-if="isPopupOpen" class="popup">
       <div>
        <button @click="closePopup" class="close-btn">&times;</button>
       </div>
       <p>Login</p>
       <form @submit.prevent="submitForm" class="registration-form">
        <div class="form-group">
          <input type="email" v-model="formData.email" placeholder="Email" required />
        </div>
        <div class="form-group">
          <input type="password" v-model="formData.password" placeholder="Password" required />
        </div>
        
        <div class="form-group">
          <button type="submit" class="submit-login-button">Login</button>
        </div>
       </form>
      </div>
    </div>

    <div class="first-container">
      <div class="left-content">
        <img src="@/assets/logomark.png" alt="Logomark" class="logomark" />
      </div>
      <div class="right-content">
        <div class="title-container">
          <h1>TRADING TANGO</h1>
        </div>
        <div class="promotion-info">
          <p>VALENTINE'S DAY PROMOTION</p>
          <p>1 - 29 February 2024</p>
          <span>*<a href="/terms-and-conditions">Terms & conditions</a> apply</span>
        </div>
      </div>
    </div>

    <div class="second-container">
      <h2>Collect All Rewards</h2>
      <div class="box-container">
        <div class="box box1">US$200 credits</div>
        <div class="box box2">INR₹2000 gift card</div>
      </div>
      <div class="box-container">
        <div class="box box3">US$400 credits</div>
        <div class="box box4">INR₹20,000 gift card</div>
      </div>
    </div>

    <div class="third-container">
      <div class="bordered-container">
        <div class="bordered-text">
          Free US$600 Credits!
        </div>

        <div class="box-container">
          <div class="third-container-circle-background">1</div>
            <div class="third-container-left-content">
              <span>US$200 credits</span>
              <p>when you open an account & deposit US$200</p>
            </div>
            <div class="third-container-right-side">
              <img src="@/assets/Promo 1B.png" alt="Promo Image" />
            </div>
        </div>
        <div class="box-container">
          <div class="third-container-circle-background">2</div>
            <div class="third-container-left-content">
              <span>US$20 credits</span>
              <p>for every lot you trade, up to 20 lots</p>
            </div>
        </div>
        <div class="box-container">
          <div class="third-container-buttons">
            <button class="register-button">Create Live Account</button>
            <button class="register-button">Download MT4 Platform</button>
          </div>
        </div>
      </div>
    </div>

    <div class="fourth-container">
      <div class="fourth-container-bordered-container">
        <div class="fourth-container-bordered-text">
          Free INR₹22,000 Gift Cards!
        </div>
  
        <div class="box-container">
          <div class="fourth-container-left-side">
            <img src="@/assets/Promo 2B.png" alt="Promo Image" />
          </div>
          <div class="fourth-container-circle-background">3</div>
          <div class="fourth-container-right-content">
            <h4>INR₹2,000 Flipkart gift card</h4>
            <p>when you refer someone</p>
            <p>to enjoy <span class="fourth-container-span">1</span></p>
          </div>
        </div>
  
        <div class="box-container">
          <div class="empty-box"></div>
          <div class="fourth-container-circle-background">4</div>
          <div class="fourth-container-right-content">
            <h4>INR₹20,000 Flipkart gift card</h4>
            <p>when you refer a second person</p>
            <p>to enjoy <span class="fourth-container-span">1</span> <span class="fourth-container-span">2</span> <span class="fourth-container-span">3</span></p>
          </div>
        </div>
  
        <div class="box-container">
          <div class="empty-box"></div>
          <div class="third-container-buttons">
            <button class="register-button">Create Live Account</button>
            <button class="register-button">Download MT4 Platform</button>
          </div>
        </div>
      </div>
    </div>

    <div class="fifth-container">
      <div class="fifth-container-content-container">
        <p>3 Easy Steps to Refer</p>
        <div class="fifth-container-step">
          <div class="fifth-container-first-step"><p>Create an account with <br> BlackWell Global & log in to <br> the Client Portal.</p></div>
          <div class="fifth-container-arrow">></div>
          <div class="fifth-container-second-step"><p>Under the "Promotion" tab, <br> copy your unique referral link <br> & send it to your referee, or <br> get your referee to scan your <br> unique QR code to create an <br> account with us.</p></div>
          <div class="fifth-container-arrow">></div>
          <div class="fifth-container-third-step"><p>Monitor your referees in the <br> Referral Activity section to <br> track whether you've fulfilled <br> the requirements for various <br> rewards!</p></div>
        </div>
      </div>
    </div>

    <div class="register-container">
      <h3>Register Now</h3>
      <div>
        <form @submit.prevent="submitForm" class="registration-form">
          <div class="form-group">
            <input type="text" v-model="formData.firstName" placeholder="First Name" required />
            <span v-if="formData.firstName.$error" class="error-message">First Name is required</span>
          </div>
          <div class="form-group">
            <input type="text" v-model="formData.lastName" placeholder="Last Name" required />
          </div>
          <div class="form-group">
            <input type="email" v-model="formData.email" placeholder="Email" required />
          </div>
          <div class="form-group">
            <div class="country-group">
              <select v-model="formData.country" required>
                <option value="" disabled selected>Country</option>
                <option value="+60">+60 Malaysia</option>
                <option value="+65">+65 Singapore</option>
              </select>
              <input type="tel" v-model="formData.phone" placeholder="Phone" required />
            </div>
          </div>
          <div class="form-group">
            <input type="password" v-model="formData.password" placeholder="Password" required />
          </div>
          <div class="form-group">
            <input type="password" v-model="formData.confirmPassword" placeholder="Confirm Password" required />
          </div>
          <div class="form-group">
            <div class="checkbox-group">
              <input type="checkbox" id="checkbox1" v-model="formData.checkbox1" required />
              <label for="checkbox1">I confirm that I am at least 18 years old.</label>
            </div>
          </div>
          <div class="form-group">
            <div class="checkbox-group">
              <input type="checkbox" id="checkbox2" v-model="formData.checkbox2" required />
              <label for="checkbox2">By joining and participating in the Competition, I acknowdledge and confirm that I have read, understood and agreed to be bound by the <a href="/terms-and-conditions">Terms & conditions</a> of the Competition.</label>
            </div>
          </div>
          <div class="form-group">
            <div class="statement-group">
              <label>This site is protected by reCAPTCHA and the Google <a href="/privacy-policy">Privacy Policy</a> and <a href="/terms-of-service">Terms of Service</a> apply.</label>
            </div>
          </div>
          <div class="form-group">
            <button type="submit" class="submit-register-button">Register Now</button>
          </div>
        </form>
        <div class="form-group">
          <div class="button-group">
            <button class="signup-facebook-button">Signup by Facebook</button>
            <button class="signup-google-button">Signup by Google</button>
          </div>
        </div>
      </div>
    </div>

    <div class="trading-guide-container">
      <h2>Trading Guides</h2>
      <div class="slideshow-container">
        <div class="slide">
          <img src="@/assets/guides_01.png" alt="Slide 1" />
          <p>Forex For Beginners</p>
        </div>
        <div class="slide">
          <img src="@/assets/guides_02.png" alt="Slide 2" />
          <p>Analysing Made Easy</p>
        </div>
        <div class="slide">
          <img src="@/assets/guides_03.png" alt="Slide 3" />
          <p>CFDs Starter Kit</p>
        </div>
        <button class="prev" @click="prevSlide">&#10094;</button>
        <button class="next" @click="nextSlide">&#10095;</button>
      </div>
    </div>

    <footer class="footer">
      <div class="footer-content">
        <div>
          <p>LOG IN TO MT4 DESKTOP APP</p>
          <button @click="downloadPlatform" class="download-platform-button">Download Platform</button>
        </div>
        <div>
          <p>LOG IN VIA MT4 MOBILE APP</p>
          <button class="app-store-button" onclick="window.location.href='https:/apps.apple.com/'"></button>
          <button class="play-store-button" onclick="window.location.href='https:/play.google.com/'"></button>
        </div>
      </div>
    </footer>

    <button @click="scrollToTop" class="scroll-to-top-button">^</button>
  </div>
</template>

<script>
import { required, email, sameAs } from '@vuelidate/validators';

export default {
  components: {
  },
  data() {
    return {
      isDropdownOpen: false,
      isPopupOpen: false,
      currentSlide: 0,

      formData: {
        firstName: '',
        lastName: '',
        email: '',
        country: '',
        phone: '',
        password: '',
        confirmPassword: '',
      },
    };
  },
  validations: {
    formData: {
      firstName: { required },
      lastName: { required },
      email: { required, email },
      country: { required },
      phone: { required },
      password: { required },
      confirmPassword: { required, sameAsPassword: sameAs('password') },
    },
  },
  methods: {
    openDropdown() {
      if (!this.isPopupOpen) {
        this.isDropdownOpen = !this.isDropdownOpen;
      }
    },
    showPopup() {
      this.isPopupOpen = true;
      this.isDropdownOpen = false;
    },
    closePopup() {
      this.isPopupOpen = false;
    },

    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    },
    scrollToRegister() {
      const registerContainer = document.querySelector(".register-container");
      registerContainer.scrollIntoView({ behavior: "smooth" });
    },

    nextSlide() {
      this.currentSlide = (this.currentSlide + 1) % 3;
      this.showSlide();
    },
    prevSlide() {
      this.currentSlide = (this.currentSlide - 1 + 3) % 3;
      this.showSlide();
    },
    showSlide() {
      const slides = document.querySelectorAll('.slide');
      slides.forEach((slide, index) => {
        slide.classList.toggle('active', index === this.currentSlide);
      });
    },

    submitForm() {
      this.$v.formData.$touch();
      if (!this.$v.formData.$error) {
        console.log('Form submitted:', this.formData);
      }
    },

    async registerUser(userData) {
      try {
        const response = await axios.post('/api/register', userData);
        console.log('User registered successfully:', response.data);
      } catch (error) {
        console.error('Registration failed:', error.response.data.error);
      }
    },

    async loginUser(credentials) {
      try {
        const response = await axios.post('/api/login', credentials);
        console.log('User logged in successfully:', response.data);
        localStorage.setItem('accessToken', response.data.accessToken);
      } catch (error) {
        console.error('Login failed:', error.response.data.error);
      }
    }
  },

  mounted() {
    this.showSlide();
},
};
</script>

<style lang="scss" scoped>
  .background-container {
    position: relative;
    overflow: hidden;
    min-height: 100vh;
  }

  .background-container::before {
    content: '';
    background-image: url('@/assets/TradingTangoHeader.png');
    background-size: cover;
    background-position: center;
    background-color: hsl(201, 100%, 35%);
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -1;
  }

  .main-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
    margin: 0 15%;
  }

  .logo-container {
    flex: 1;
    max-width: 25%;
    margin-right: 50px;
  }
  
  .logo {
    max-width: 80%;
  }
  
  .countdown-container {
    flex: 1;
    color: white;
    width: fit-content;
  }

  .countdown-container p {
    font-size: 12px;
  }
  
  .countdowntime-container {
    display: flex;
    color: white;
    margin-right: 13%;
  }

  .countdown-group {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-right: 25px;
  }

  .countdowntime-container-p1 {
      font-size: 27px;
      margin-top: 0;
      margin-bottom: 5px;
  }

  .countdowntime-container-p2 {
      font-size: 9px;
      text-align: center;
  }

  .user-actions {
    display: flex;
    align-items: center;
  }
  
  .register-button {
    background-color: #f68b1f;
    color: white;
    border: none;
    padding: 10px 20px;
    margin-right: 10px;
    border-radius: 25px;
    cursor: pointer;
  }

  .register-button:hover {
    background-color: #d76d17;
  }
  
  .user-icon {
    position: relative;
    cursor: pointer;
    width: 30px;
    height: 30px;
  }
  
  .dropdown {
    right: 0;
    background: rgb(43, 43, 43);
    padding: 10px;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }
  
  .dropdown button{
    color: white;
    background: rgb(43, 43, 43);
    border: none;
  }

  .user-dropdown {
    position: absolute;
    top: 30px;
    left: -10%;
    background: white;
    padding: 10px;
    border: 1px solid #ccc;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }
  
  .popup {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    padding: 20px;
    border: 1px solid #ccc;
    z-index: 1000;
  }

  .close-btn {
    position: absolute;
    top: 10px;
    right: 10px;
    cursor: pointer;
  }

  .close-btn:hover {
    color: red;
  }

  .submit-login-button {
    background-color: grey;
    width: 100%;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 25px;
    align-items: center;
    cursor: pointer;
  }

  .submit-login-button:hover {
    background-color: #d76d17;
  }

  .first-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
    margin: 0 15%;
    margin-top: 20px;
  }

  .logomark {
    max-width: 100%;
    width: auto;
  }

  .left-content {
    flex: 1;
    max-width: 20%;
    margin-left: 5%;
    margin-top: 2%;
    display: flex;
    align-items: center;
  }

  .right-content {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    margin-left: 20px;
    align-items: center;
  }

  .title-container {
    margin: 0%;
  }

  .title-container h1 {
    font-size: 60px;
    font-family: 'ATRotisSemiSans-ExtraBold', sans-serif;
    font-weight: 400;
    color: #b9e6f9;
    margin: 0;
  }

  .promotion-info {
    text-align: center;
  }

  .promotion-info p {
    color: #b9e6f9;
    font-size: 30px;
    font-family: 'ATRotisSemiSans-ExtraBold', sans-serif;
    margin: 0;
  }

  .promotion-info span {
    color: #b9e6f9;
    font-size: 10px;
  }

  .promotion-info a {
    color: #f68b1f;
    font-size: 10px;
    font-family: 'ATRotisSemiSans-ExtraBold', sans-serif;
  }
  
  .second-container h2 {
    color: #f68b1f;
    font-size: 30px;
    font-weight: 550;
    font-family: 'ATRotisSemiSans-Light', sans-serif;
  }

  .second-container {
    margin: 0 15%;
    padding: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: fit-content;
  }

  .box-container {
    display: flex;
  }

  .box {
    flex: 1;
    height: 60px;
    width: 450px;
    border: 1px solid #000;
    border-radius: 5px;
    margin: 10px;
    box-sizing: border-box;
    color: #f68b1f;
    text-align: center;
    font-size: 20px;
    font-weight: 400;
    display: flex;
    flex-direction: column;
    justify-content: center;

    background: linear-gradient(rgba(38, 50, 79, 0.5), rgba(46, 64, 105, 0.5)), url('@/assets/logo_side.png') no-repeat right top; 
    background-size: auto 100%;
  }

  .third-container {
    margin: 0 15%;
    margin-top: 100px;
    padding: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: fit-content;
  }

  .bordered-container {
    position: relative;
    border: 1px solid #f68b1f;
    padding: 10px;
    height: 260px;
    width: 920px;
  }

  .bordered-text {
    margin: -25px 50px;
    color: white;
    font-size: 25px;
    height: fit-content;
    width: fit-content;
    margin-bottom: 10px;
  }

  .third-container-circle-background {
    width: 20px;
    height: 20px;
    background-color: #f68b1f;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: black;
    font-size: 20px;
    margin-left: 30px;
    margin-right: 20px;
    margin-top: 35px;
  }

  .third-container-left-content {
    flex: 1;
    color: white;
    margin-top: 31px;
  }

  .third-container-left-content span { 
    margin: 0%;
    font-weight: 600;
    color: #f68b1f;
  }

  .third-container-left-content p {
    margin: 0%;
    margin-top: 6px;
    font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    color: white;
  }

  .third-container-buttons {
    display: flex;
    justify-content: space-around;
    margin-top: 30px;
    margin-left: 42px;
  }

  .third-container-right-side {
    align-self: flex-end;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: flex-end;
  }

  .third-container-right-side img {
    margin: -170px 50px;
    width: 350px;
    height: 350px;
    align-self: flex-end;
  }

  .fourth-container {
    margin: 0 15%;
    margin-top: 100px;
    padding: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: fit-content;
  }

  .fourth-container-bordered-container {
    position: relative;
    border: 1px solid #f68b1f;
    padding: 10px;
    height: 300px;
    width: 920px;
  }

  .fourth-container-bordered-text {
    margin: -25px 130px;
    color: white;
    font-size: 25px;
    float: right;
    height: fit-content;
    width: fit-content;
  }

  .fourth-container-left-side {
    align-self: flex-end;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: flex-end;
  }

  .fourth-container-left-side img {
    margin: -170px 50px;
    width: 350px;
    height: 350px;
    align-self: flex-end;
  }

  .fourth-container-circle-background {
    width: 20px;
    height: 20px;
    background-color: #f68b1f;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: black;
    font-size: 20px;
    margin-left: 30px;
    margin-right: 20px;
    margin-top: 35px;
  }

  .fourth-container-right-content {
    flex: 1;
    color: white;
    margin-top: 31px;
  }

  .fourth-container-right-content h4 { 
    margin: 0%;
    font-weight: 600;
    color: #f68b1f;
  }

  .fourth-container-right-content p {
    margin: 0%;
    margin-top: 6px;
    font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    color: white;
  }

  .empty-box {
    width: 450px;
  }

  .fourth-container-span {
    width: 20px;
    height: 20px;
    background-color: #f68b1f;
    border-radius: 50%;
    align-items: center;
    justify-content: center;
    color: black;
    font-size: 20px;
  }

  .fifth-container {
    background-image: url('@/assets/easy_step_bg.png');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    padding: 20px;
    box-sizing: border-box;
    margin-top: 50px;
  }

  .fifth-container-content-container {
    margin: 0 15%;
    margin-top: 45px;
    padding: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
    height: fit-content;
  }

  .fifth-container-content-container p { 
    margin: 0%;
    margin-left: 50px;
    margin-bottom: 50px;
    float: left;
    font-size: 20px;
    color: white;
  }
  
  .fifth-container-step {
    margin-bottom: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  }

  .fifth-container-first-step p,
  .fifth-container-second-step p,
  .fifth-container-third-step p {
    margin-top: 70px;
    margin-left: 25px;
    margin-right: 25px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    font-size: 14px;
  }

  .fifth-container-first-step {
    background-image: url('@/assets/Step01.png');
    background-size: contain;
    background-repeat: no-repeat;
    width: 300px;
    height: 200px;
    color: white;
    margin: 0 20px;
  }

  .fifth-container-second-step {
    background-image: url('@/assets/Step02.png');
    background-size: contain;
    background-repeat: no-repeat;
    width: 300px;
    height: 200px;
    color: white;
    margin: 0 20px;
  }
  
  .fifth-container-third-step {
    background-image: url('@/assets/Step03.png');
    background-size: contain;
    background-repeat: no-repeat;
    width: 300px;
    height: 200px;
    color: white;
    margin: 0 20px;
  }

  .fifth-container-arrow {
    color: #f68b1f;
    font-size: 60px;
    margin: 0 10px;
  }

  .register-container {
    justify-content: space-between;
    align-items: center;
    padding: 20px;
    margin: 0 19%;
  }

  .register-container h3{
    color: #f68b1f;
    font-family: 'ATRotisSemiSans-Light', sans-serif;
  }

  .registration-form {
    justify-content: space-between;
    width: 100%;
  }

  .form-group {
    margin-bottom: 15px;
  }

  .form-group input,
  .form-group select {
    width: 100%;
    padding: 10px;
    box-sizing: border-box;
    margin-bottom: 5px;
    background-color: #204c9783;
    color: white;
  }

  .registration-form input::placeholder {
    color: rgba(255, 255, 255, 0.753);
  }

  .country-group {
    display: flex;
  }

  .country-group input {
    width: 90%;
    margin-left: 1%;
  }

  .country-group select {
    width: 10%;
    margin-right: 1%;
  }

  .checkbox-group {
    width: 100%;
    display: flex;
    align-items: center;
    margin-top: 30px;
    margin-bottom: 5px;
  }

  .checkbox-group input[type="checkbox"] {
    width: 5%;
  }

  .checkbox-group label {
    width: 95%;
    color: rgba(255, 255, 255, 0.466);
    font-size: 14px;
  }

  .statement-group a, .checkbox-group a {
    color: rgba(255, 255, 255, 0.619);
    font-size: 14px;
  }

  .statement-group {
    width: 100%;
    display: flex;
    align-items: center;
    margin-top: 30px;
    margin-bottom: 5px;
  }

  .statement-group label {
    color: white;
    font-size: 14px;
  }

  .statement-group a {
    color: rgba(255, 255, 255, 0.785);
    font-size: 14px;
  }

  .submit-register-button {
    background-color: grey;
    width: 96.5%;
    color: white;
    border: none;
    margin-left: 16px;
    padding: 10px 20px;
    border-radius: 25px;
    align-items: center;
    cursor: pointer;
  }

  .submit-register-button:hover {
    background-color: #d76d17;
  }

  .button-group {
    width: 100%;
    display: flex;
    align-items: center;
    margin-top: 20px;
    margin-bottom: 5px;
  }

  .signup-facebook-button {
    width: 46%;
    margin: auto;
    padding: 7px;
    color: white;
    background: #284fab;
    cursor: pointer;
    border: none;
    border-radius: 5%;
  }

  .signup-google-button {
    width: 46%;
    margin: auto;
    padding: 7px;
    color: white;
    background: red;
    cursor: pointer;
    border: none;
    border-radius: 5%;
  }

  .trading-guide-container h2 {
    color: #f68b1f;
    font-size: 30px;
    font-weight: 550;
    font-family: 'ATRotisSemiSans-Light', sans-serif;
  }

  .trading-guide-container {
    margin: 0 15%;
    padding: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: fit-content;
    position: relative;
  }

  .slideshow-container {
    position: relative;
    display: flex;
    justify-content: space-between;
    margin-bottom: 50px;
  }

  .slide {
    flex: 0 0 30%;
    box-sizing: border-box;
    margin: 0%;
  }

  .slide img {
    width: 90%;
    margin-left: 10px;
  }

  .slide p {
    margin: -40px 30px;
    padding: 5%;
    width: 250px;
    height: 10px;
    color: white;
    text-align: center;
    background: rgba(245, 149, 31, 0.848);
    position: relative;
    margin-right: 20px;
  }
  
  .prev, .next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    font-size: 20px;
    padding: 10px;
    border-radius: 10%;
    background: rgba(139, 139, 139, 0.7);
    color: white;
    border: none;
    cursor: pointer;
  }

  .prev {
    left: 0;
  }

  .next {
    right: 0;
  }

  .footer {
    background-color: #242530f4;
    color: white;
    margin-top: 40px;
    padding: 20px;
    text-align: center;
  }

  .footer-content {
    justify-content: space-around;
    align-items: center;
    margin-bottom: 20px;
  }

  .footer-content p {
    font-family: 'ATRotisSemiSans-Light', sans-serif;
    margin-top: 30px;
    margin-bottom: 30px;
  }

  .download-platform-button {
    background-color: #f68b1f;
    color: white;
    border: none;
    width: 500px;
    padding: 10px 20px;
    margin-right: 10px;
    border-radius: 25px;
    cursor: pointer;
    font-size: 20px;
    font-weight: 500;
  }

  .download-platform-button:hover {
    background-color: #d76d17;
  }

  .app-store-button {
    background-image: url('@/assets/app-store.png');
    background-size: cover;
    background-position: center;
    width: 170px;
    height: 50px;
    color: white;
    border-color: #b9e6f9;
    border-radius: 10px;
    cursor: pointer;
    margin-right: 50px;
  }

  .play-store-button {
    background-image: url('@/assets/google-play.png');
    background-size: cover;
    background-position: center;
    width: 170px;
    height: 50px;
    margin-left: 50px;
    color: white;
    border-color: #b9e6f9;
    border-radius: 10px;
    cursor: pointer;
  }

  .scroll-to-top-button {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: #f68b1f;
    margin-left: 50px;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 25px;
    cursor: pointer;
  }

  .scroll-to-top-button:hover {
    background-color: #d76d17;
  }
</style>
