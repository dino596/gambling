---
layout: base
title: Student Home 
description: Home Page
hide: true
---


<style>
    .classcode-container {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap; /* allows the cards to wrap onto the next line if the screen is too small */
    }
    
    .classcode-card {
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
    
    .classcode-card h1 {
        margin-bottom: 20px;
    }
</style>

<div class="classcode-container">
    <!-- Login Form -->
    <div class="classcode-card">
        <h1>Class Code</h1>
        <form id="classcodeForm" onsubmit="handleLogin(event);">
            <p>
                <label>
                    Code:
                    <input type="password" name="password" id="password" required>
                </label>
            </p>
            <p>
                <button type="submit">Submit</button>
            </p>
  <!--          <p id="loginMessage" style="color: red;"></p>  -->
        </form>
    </div>
<script>
// add backend + javascript code
</script>