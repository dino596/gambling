---
layout: page
title: Login
permalink: /login/
search_exclude: true
show_reading_time: false
---

<style>
    .login-container {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap; /* allows the cards to wrap onto the next line if the screen is too small */
    }
    
    .login-card {
        margin-top: 0;
        width: 45%;
        border: 1px solid #ddd;
        border-radius: 5px;
        padding: 20px;
        box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
        margin-bottom: 20px;
        overflow-x: auto;
        text-align: center;
    }
    
    .login-card h1 {
        margin-bottom: 20px;
    }
</style>

<div class="login-container">
    <!-- Login Form -->
    <div class="login-card">
        <h1>User Login</h1>
        <form id="loginForm" onsubmit="handleLogin(event);">
            <p>
                <label>
                    GitHub ID:
                    <input type="text" name="uid" id="uid" required>
                </label>
            </p>
            <p>
                <label>
                    Password:
                    <input type="password" name="password" id="password" required>
                </label>
            </p>
            <p>
                <button type="submit">Login</button>
            </p>
            <p id="loginMessage" style="color: red;"></p>
        </form>
    </div>
<script>
// Handle login request
function handleLogin(event) {
    event.preventDefault(); // Prevent default form submission
    const uid = document.getElementById("uid").value;
    const password = document.getElementById("password").value;
    fetch('https://your-api-endpoint/api/authenticate', { // Update the API endpoint
        method: "POST",
        headers: {
            "Content-Type": "application/json"
        },
        body: JSON.stringify({ uid, password })
    })
    .then(response => {
        if (!response.ok) {
            throw new Error(`Login failed: ${response.status}`);
        }
        return response.json();
    })
    .then(data => {
        document.getElementById("loginMessage").textContent = "Login successful!";
        window.location.href = '/profile'; // Redirecting to profile after successful login
    })
    .catch(error => {
        console.error("Login Error:", error);
        document.getElementById("loginMessage").textContent = `Login Error: ${error.message}`;
    });
}
</script>