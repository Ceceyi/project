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
        <button @click="openDropdown" class="register-button">REGISTER NOW</button>
        <div v-if="isDropdownOpen || isPopupOpen" :class="{ 'dropdown': isDropdownOpen, 'user-dropdown': isPopupOpen }">
          <button v-if="isDropdownOpen" @click="showPopup">Login</button>
          <!-- Add other dropdown items if needed -->
        </div>
        <img src="@/assets/people-icon.png" alt="User Icon" @click="openDropdown" class="user-icon" />
      </div>
       
      <!-- Popup for Login -->
      <div v-if="isPopupOpen" class="popup">
       <p>Popup Content for Login</p>
       <!-- Add your login form or content here -->
       <button @click="closePopup">Close</button>
      </div>
    </div>

    <div class="first-container">
      <!-- Left side content with picture -->
      <div class="left-content">
        <img src="@/assets/logomark.png" alt="Logomark" class="logomark" />
      </div>

      <!-- Right side content -->
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

  </div>
</template>

<script>

export default {
  components: {
  },
  data() {
    return {
      isDropdownOpen: false,
      isPopupOpen: false,
  };
  },
  methods: {
    openDropdown() {
      // Toggle between dropdown and popup
      if (!this.isPopupOpen) {
        this.isDropdownOpen = !this.isDropdownOpen;
      }
    },
    showPopup() {
      this.isPopupOpen = true;
      this.isDropdownOpen = false; // Close the dropdown when opening the popup
    },
    closePopup() {
      this.isPopupOpen = false;
    },
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
      margin-right: 25px; /* Adjust the spacing between countdown groups */
  }

  .countdowntime-container-p1 {
      font-size: 27px;
      margin-top: 0;
      margin-bottom: 5px;
  }

  .countdowntime-container-p2 {
      font-size: 9px;
      text-align: center; /* Center the text below the countdown numbers */
  }

  .main-content {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .main-footer {
    background-color: #333;
    color: white;
    padding: 20px;
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
    width: 30px; /* Adjust the width as needed */
    height: 30px; /* Adjust the height as needed */
  }
  
  .dropdown {
    right: 0;
    background: white;
    padding: 10px;
    border: 1px solid #ccc;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }
  
  .user-dropdown {
    position: absolute;
    top: 30px; /* Adjust the value to control the distance between the user icon and the dropdown */
    left: 0; /* Adjust the value to control the distance from the left side */
    background: white;
    padding: 10px;
    border: 1px solid #ccc;
    display: flex;
    flex-direction: column;
    align-items: flex-start; /* Align dropdown items to the left */
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
    width: 900px;
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
    width: 900px;
  }

  .fourth-container-bordered-text {
    margin: -25px 50px;
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
</style>
