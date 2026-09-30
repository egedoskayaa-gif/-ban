<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ödeme Bilgileri</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #f4f6f8;
      font-family: Arial, sans-serif;
      padding: 20px;
    }

    .card {
      width: 100%;
      max-width: 430px;
      background: white;
      border-radius: 18px;
      padding: 30px 24px;
      box-shadow: 0 8px 30px rgba(0,0,0,0.08);
      text-align: center;
    }

    h1 {
      margin-top: 0;
      font-size: 24px;
      color: #222;
    }

    .iban {
      margin: 25px 0 18px;
      padding: 16px;
      background: #f1f3f5;
      border-radius: 10px;
      font-size: 17px;
      font-weight: bold;
      word-break: break-all;
      color: #222;
    }

    button {
      width: 100%;
      border: none;
      border-radius: 10px;
      padding: 15px;
      background: #111827;
      color: white;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
    }

    button:hover {
      background: #374151;
    }

    #message {
      margin-top: 12px;
      color: #16803c;
      font-size: 14px;
      min-height: 20px;
    }
  </style>
</head>

<body>

  <div class="card">
    <h1>Ödeme Bilgileri</h1>

    <div class="iban" id="iban">
      TR00 0000 0000 0000 0000 0000 00
    </div>

    <button onclick="copyIBAN()">
      IBAN'ı Kopyala
    </button>

    <div id="message"></div>
  </div>

  <script>
    function copyIBAN() {
      const iban = document.getElementById("iban").innerText
        .replace(/\s/g, "");

      navigator.clipboard.writeText(iban).then(() => {
        document.getElementById("message").innerText =
          "✓ IBAN kopyalandı";
      });
    }
  </script>

</body>
</html>
