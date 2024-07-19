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
