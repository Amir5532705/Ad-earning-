# Ad-earning-
Watch ad and earn
!DOCTYPE html><html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Subscription Page</title>
    <style>
        body { font-family: Arial, sans-serif; background-color: #f4f4f4; padding: 20px; }
        .container { max-width: 600px; margin: auto; background: white; padding: 20px; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
        .login-btns button { margin: 10px; padding: 10px 20px; font-size: 16px; }
        .subscription-option { border: 1px solid #ccc; padding: 15px; border-radius: 6px; margin-bottom: 15px; background-color: #fafafa; }
        .subscribe-btn { background-color: green; color: white; padding: 10px; border: none; border-radius: 4px; cursor: pointer; }
    </style>
</head>
<body>
    <div class="container">
        <h2>Login</h2>
        <div class="login-btns">
            <button onclick="loginWith('google')">Login with Google</button>
            <button onclick="loginWith('facebook')">Login with Facebook</button>
        </div><div id="subscription" style="display:none;">
        <h2>Select Subscription</h2>

        <div class="subscription-option">
            <h3>₨600 Package</h3>
            <p>Watch ads daily to earn ₨75.</p>
            <button class="subscribe-btn" onclick="subscribe(600)">Subscribe via JazzCash/EasyPaisa</button>
        </div>

        <div class="subscription-option">
            <h3>₨1500 Package</h3>
            <p>Watch 30s ads daily to earn ₨200.</p>
            <button class="subscribe-btn" onclick="subscribe(1500)">Subscribe via JazzCash/EasyPaisa</button>
        </div>
    </div>
</div>

<script>
    function loginWith(provider) {
        alert("Simulating login with " + provider);
        document.getElementById("subscription").style.display = "block";
    }

    function subscribe(amount) {
        alert("Redirecting to JazzCash / EasyPaisa for Rs. " + amount);
        // Placeholder


