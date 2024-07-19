# Login-page
The login page is a secure and user-friendly interface designed to authenticate users before granting access to a web application. It uses a combination of HTML for the structure, CSS for the styling, and JavaScript for interactivity and validation.

H T M L

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Validation</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="./login.css">
    <script defer src="./login.js"></script>
</head>



<body>

    <nav>
    
        <b>CODING LAB</b>
        <p style="display: inline;">Home</p>
        <p style="display: inline;">Product</p>
        <p style="display: inline;">Services</p>
        <p style="display: inline;">Contact</p>
       
      </nav>
    


    <div class="container">
        <form id="form" action="/">
            <h1>Registration</h1>
            <div class="input-control">
                <label for="username">Username</label>
                <input id="username" name="username" type="text">
                <div class="error"></div>
            </div>
            <div class="input-control">
                <label for="email">Email</label>
                <input id="email" name="email" type="text">
                <div class="error"></div>
            </div>
            <div class="input-control">
                <label for="password">Password</label>
                <input id="password"name="password" type="password">
                <div class="error"></div>
            </div>
            <div class="input-control">
                <label for="password2">Password again</label>
                <input id="password2"name="password2" type="password">
                <div class="error"></div>
            </div>
            <button type="submit">Login</button><br>
            <button type="submit">Register</button>
        </form>
    </div>
</body>
</html>



C S S

body {
    background: linear-gradient(to right, #0f2027, #203a43, #2c5364);
    font-family: 'Poppins', sans-serif;
}

 
nav {
    display: flex;
    justify-content: space-around;
    align-items: center;
    height: 15vh;


  }



#form {
    width: 300px;
    margin: 5vh auto 0 auto;
    padding: 30px;
    background-color: whitesmoke;
    border-radius: 4px;
    font-size: 12px;
}

#form h1 {
    color: #0f2027;
    text-align: center;
}

#form button {
    padding: 10px;
    margin-top: 10px;
    width: 100%;
    color: white;
    background-color: rgb(41, 57, 194);
    border: none;
    border-radius: 4px;
}

.input-control {
    display: flex;
    flex-direction: column;
}

.input-control input {
    border: 2px solid #f0f0f0;
	border-radius: 4px;
	display: block;
	font-size: 12px;
	padding: 10px;
	width: 100%;
}

.input-control input:focus {
    outline: 0;
}

.input-control.success input {
    border-color: #09c372;
}

.input-control.error input {
    border-color: #ff3860;
}

.input-control .error {
    color: #ff3860;
    font-size: 9px;
    height: 13px;
}


J A V A  S C R I P T

const form = document.getElementById('form');
const username = document.getElementById('username');
const email = document.getElementById('email');
const password = document.getElementById('password');
const password2 = document.getElementById('password2');

form.addEventListener('submit', e => {
    e.preventDefault();

    validateInputs();
});

const setError = (element, message) => {
    const inputControl = element.parentElement;
    const errorDisplay = inputControl.querySelector('.error');

    errorDisplay.innerText = message;
    inputControl.classList.add('error');
    inputControl.classList.remove('success')
}

const setSuccess = element => {
    const inputControl = element.parentElement;
    const errorDisplay = inputControl.querySelector('.error');

    errorDisplay.innerText = '';
    inputControl.classList.add('success');
    inputControl.classList.remove('error');
};

const isValidEmail = email => {
    const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(String(email).toLowerCase());
}

const validateInputs = () => {
    const usernameValue = username.value.trim();
    const emailValue = email.value.trim();
    const passwordValue = password.value.trim();
    const password2Value = password2.value.trim();

    if(usernameValue === '') {
        setError(username, 'Username is required');
    } else {
        setSuccess(username);
    }

    if(emailValue === '') {
        setError(email, 'Email is required');
    } else if (!isValidEmail(emailValue)) {
        setError(email, 'Provide a valid email address');
    } else {
        setSuccess(email);
    }

    if(passwordValue === '') {
        setError(password, 'Password is required');
    } else if (passwordValue.length < 8 ) {
        setError(password, 'Password must be at least 8 character.')
    } else {
        setSuccess(password);
    }

    if(password2Value === '') {
        setError(password2, 'Please confirm your password');
    } else if (password2Value !== passwordValue) {
        setError(password2, "Passwords doesn't match");
    } else {
        setSuccess(password2);
    }

};
