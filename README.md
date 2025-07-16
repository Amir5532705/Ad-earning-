<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Ad Earning App</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      padding: 20px;
    }
    .subscription-option, #ads-section {
      margin: 20px 0;
    }
    .subscribe-btn {
      padding: 10px 20px;
      margin: 10px;
    }
  </style>
</head>
<body>
  <h2>Login</h2>
  <button onclick="loginWithGoogle()">Login with Google</button>  <div id="subscription" style="display:none;">
    <h2>Select Subscription</h2><div class="subscription-option">
  <h3>₨600 Package</h3>
  <p>Watch ads daily to earn ₨75.</p>
  <button class="subscribe-btn" onclick="subscribe(600)">Subscribe via JazzCash/EasyPaisa</button>
</div>

<div class="subscription-option">
  <h3>₨1500 Package</h3>
  <p>Watch 30s ads daily to earn ₨200.</p>
  <button class="subscribe-btn" onclick="subscribe(1500)">Subscribe via JazzCash/EasyPaisa</button>
</div>

<div class="subscription-option">
  <h3>₨700 Package (Premium)</h3>
  <p>Watch YouTube ads daily to earn ₨50.</p>
  <button class="subscribe-btn" onclick="subscribe(700)">Subscribe and Start Watching Ads</button>
</div>

  </div>  <div id="ads-section" style="display:none;">
    <h2>Watch Ad</h2>
    <iframe width="560" height="315"
      src="https://www.youtube.com/embed/dQw4w9WgXcQ"
      frameborder="0" allow="autoplay; encrypted-media" allowfullscreen>
    </iframe>
    <br>
    <button onclick="completeAd()">I Watched the Ad</button>
  </div>  <!-- Firebase SDKs -->  <script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js"></script>  <script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-auth.js"></script>  <script>
    // ❌ Replace these values with your actual Firebase config
    const firebaseConfig = {
      apiKey: "YOUR_API_KEY",
      authDomain: "YOUR_PROJECT.firebaseapp.com",
      projectId: "YOUR_PROJECT_ID",
      appId: "YOUR_APP_ID"
    };

    firebase.initializeApp(firebaseConfig);
    const provider = new firebase.auth.GoogleAuthProvider();

    function loginWithGoogle() {
      firebase.auth().signInWithPopup(provider)
        .then((result) => {
          const user = result.user;
          alert("Welcome, " + user.displayName);
          document.getElementById("subscription").style.display = "block";
        })
        .catch((error) => {
          console.error("Login Error:", error);
        });
    }

    function subscribe(amount) {
      alert("Payment of Rs. " + amount + " done via JazzCash/EasyPaisa");
      if (amount === 700) {
        document.getElementById("ads-section").style.display = "block";
      }
    }

    function completeAd() {
      alert("You earned Rs. 50 for watching this ad. Come back tomorrow!");
    }
  </script></body>
</html>
