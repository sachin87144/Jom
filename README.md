<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Personal Web Space</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            width: 100%;
            max-width: 900px;
            background-color: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            overflow: hidden;
        }

        .form-container {
            padding: 40px;
            transition: all 0.5s ease;
        }

        h2 {
            text-align: center;
            margin-bottom: 25px;
            color: #333;
        }

        .input-group {
            margin-bottom: 20px;
            position: relative;
        }

        input {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: border 0.3s;
        }

        input:focus {
            outline: none;
            border-color: #1a2a6c;
            box-shadow: 0 0 5px rgba(26, 42, 108, 0.3);
        }

        button {
            width: 100%;
            padding: 12px;
            background: linear-gradient(to right, #1a2a6c, #b21f1f);
            border: none;
            border-radius: 8px;
            color: white;
            font-size: 16px;
            cursor: pointer;
            transition: opacity 0.3s;
        }

        button:hover {
            opacity: 0.9;
        }

        .error {
            color: #e74c3c;
            font-size: 14px;
            margin-top: 5px;
            display: none;
        }

        .dashboard {
            padding: 30px;
            display: none;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }

        .welcome {
            text-align: left;
        }

        .welcome h2 {
            margin-bottom: 5px;
            text-align: left;
        }

        .last-login {
            background-color: #f8f9fa;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            text-align: center;
        }

        .last-login p {
            margin: 5px 0;
            color: #555;
        }

        .logout-btn {
            background: linear-gradient(to right, #e74c3c, #e67e22);
            width: auto;
            padding: 8px 15px;
        }

        .user-info {
            background-color: #f0f8ff;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
        }

        .user-info p {
            margin: 8px 0;
            color: #444;
        }

        .content-area {
            margin-top: 30px;
        }

        .content-area h3 {
            margin-bottom: 15px;
            color: #333;
        }

        textarea {
            width: 100%;
            height: 200px;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            resize: vertical;
            transition: border 0.3s;
        }

        textarea:focus {
            outline: none;
            border-color: #1a2a6c;
            box-shadow: 0 0 5px rgba(26, 42, 108, 0.3);
        }

        .save-btn {
            background: linear-gradient(to right, #1a2a6c, #b21f1f);
            width: auto;
            padding: 10px 20px;
            margin-top: 10px;
        }

        .saved-message {
            color: #27ae60;
            margin-top: 10px;
            display: none;
        }

        @media (max-width: 768px) {
            .container {
                max-width: 95%;
            }
            
            .form-container, .dashboard {
                padding: 20px;
            }
            
            .header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .logout-btn {
                margin-top: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Login Form -->
        <div class="form-container" id="loginForm">
            <h2>Welcome to Personal my web</h2>
            <div class="input-group">
                <input type="text" id="username" placeholder="Username" required>
                <div class="error" id="usernameError">Please enter a valid username (min 3 characters)</div>
            </div>
            <div class="input-group">
                <input type="password" id="password" placeholder="Password" required>
                <div class="error" id="passwordError">Password must be at least 6 characters</div>
            </div>
            <button id="loginBtn">Login</button>
            <div class="input-group" style="text-align: center; margin-top: 15px;">
                <p>sahi se bharna prutha bhen</p>
            </div>
        </div>

        <!-- Dashboard -->
        <div class="dashboard" id="dashboard">
            <div class="header">
                <div class="welcome">
                    <h2>Welcome, <span id="userDisplayName">User</span>!</h2>
                    <p>This is your personal web space</p>
                </div>
                <button class="logout-btn" id="logoutBtn">Logout</button>
            </div>
            
            <div class="last-login">
                <h3>Last Login Information</h3>
                <p>Your last login was on:</p>
                <p id="lastLoginDate">Never</p>
            </div>
            
            <div class="user-info">
                <h3>Account Information</h3>
                <p>Username: <span id="displayUsername">user123</span></p>
                <p>Account created: <span id="accountCreated">Today</span></p>
            </div>
            
            <div class="content-area">
                <h3>Your Personal Notes</h3>
                <p>You can write and save your personal notes here:</p>
                <textarea id="personalNotes" placeholder="Start typing your notes here..."></textarea>  <h3>write your answer sister</h3>
                <p>ap yaha par apne bichar likho:</p>
                <textarea id="answer"placeholder="now type here..."></textarea>
                <button class="save-btn" id="saveNotesBtn">Save Notes</button>
                <div class="saved-message" id="savedMessage">Notes saved successfully!</div>
            </div>
        </div>
    </div>

    <script>
        // DOM Elements
        const loginForm = document.getElementById('loginForm');
        const dashboard = document.getElementById('dashboard');
        const loginBtn = document.getElementById('loginBtn');
        const logoutBtn = document.getElementById('logoutBtn');
        const usernameInput = document.getElementById('username');
        const passwordInput = document.getElementById('password');
        const usernameError = document.getElementById('usernameError');
        const passwordError = document.getElementById('passwordError');
        const userDisplayName = document.getElementById('userDisplayName');
        const displayUsername = document.getElementById('displayUsername');
        const lastLoginDate = document.getElementById('lastLoginDate');
        const accountCreated = document.getElementById('accountCreated');
        const personalNotes = document.getElementById('personalNotes');
        const saveNotesBtn = document.getElementById('saveNotesBtn');
        const savedMessage = document.getElementById('savedMessage');

        // Default credentials
        const DEFAULT_USERNAME = "Sachin";
        const DEFAULT_PASSWORD = "radhe radhe";

        // Check if user is already logged in
        document.addEventListener('DOMContentLoaded', function() {
            const savedUser = localStorage.getItem('currentUser');
            if (savedUser) {
                const user = JSON.parse(savedUser);
                showDashboard(user);
                
                // Load saved notes
                const savedNotes = localStorage.getItem(`notes_${user.username}`);
                if (savedNotes) {
                    personalNotes.value = savedNotes;
                }
            }
        });

        // Login functionality
        loginBtn.addEventListener('click', function() {
            const username = usernameInput.value.trim();
            const password = passwordInput.value.trim();
            
            // Reset errors
            usernameError.style.display = 'none';
            passwordError.style.display = 'none';
            
            // Validate inputs
            let isValid = true;
            
            if (username.length < 3) {
                usernameError.textContent = 'Username must be at least 3 characters';
                usernameError.style.display = 'block';
                isValid = false;
            }
            
            if (password.length < 6) {
                passwordError.textContent = 'Password must be at least 6 characters';
                passwordError.style.display = 'block';
                isValid = false;
            }
            
            if (!isValid) return;
            
            // Check credentials (in a real app, this would connect to a server)
            if (username === DEFAULT_USERNAME && password === DEFAULT_PASSWORD) {
                // Successful login with default credentials
                handleSuccessfulLogin(username);
            } else {
                // Check if user exists in localStorage
                let users = JSON.parse(localStorage.getItem('users')) || {};
                
                if (users[username] && users[username].password === password) {
                    // Successful login with stored user
                    handleSuccessfulLogin(username);
                } else {
                    // Invalid credentials
                    passwordError.textContent = 'Invalid username or password';
                    passwordError.style.display = 'block';
                }
            }
        });

        function handleSuccessfulLogin(username) {
            // Get or create user data in localStorage
            let users = JSON.parse(localStorage.getItem('users')) || {};
            
            if (!users[username]) {
                // New user
                users[username] = {
                    username: username,
                    displayName: username.charAt(0).toUpperCase() + username.slice(1),
                    accountCreated: new Date().toLocaleDateString(),
                    lastLogin: null,
                    password: passwordInput.value // In a real app, passwords should be hashed
                };
            } else {
                // Update last login for existing user
                users[username].lastLogin = new Date().toISOString();
            }
            
            // Save updated user data
            localStorage.setItem('users', JSON.stringify(users));
            
            // Set current user
            localStorage.setItem('currentUser', JSON.stringify(users[username]));
            
            // Show dashboard
            showDashboard(users[username]);
            
            // Load saved notes for this user
            const savedNotes = localStorage.getItem(`notes_${username}`);
            if (savedNotes) {
                personalNotes.value = savedNotes;
            }
        }

        // Logout functionality
        logoutBtn.addEventListener('click', function() {
            localStorage.removeItem('currentUser');
            showLoginForm();
        });

        // Save notes functionality
        saveNotesBtn.addEventListener('click', function() {
            const currentUser = JSON.parse(localStorage.getItem('currentUser'));
            if (currentUser) {
                localStorage.setItem(`notes_${currentUser.username}`, personalNotes.value);
                
                // Show saved message
                savedMessage.style.display = 'block';
                setTimeout(function() {
                    savedMessage.style.display = 'none';
                }, 2000);
            }
        });

        // Show dashboard
        function showDashboard(user) {
            loginForm.style.display = 'none';
            dashboard.style.display = 'block';
            
            // Update user info
            userDisplayName.textContent = user.displayName;
            displayUsername.textContent = user.username;
            accountCreated.textContent = user.accountCreated;
            
            // Format and display last login
            if (user.lastLogin) {
                const lastLogin = new Date(user.lastLogin);
                lastLoginDate.textContent = lastLogin.toLocaleString();
            } else {
                lastLoginDate.textContent = 'This is your first login!';
            }
        }

        // Show login form
        function showLoginForm() {
            dashboard.style.display = 'none';
            loginForm.style.display = 'block';
            
            // Clear form
            usernameInput.value = '';
            passwordInput.value = '';
            usernameError.style.display = 'none';
            passwordError.style.display = 'none';
        }

        // Allow login with Enter key
        passwordInput.addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                loginBtn.click();
            }
        });
    </script>
</body>
</html>
