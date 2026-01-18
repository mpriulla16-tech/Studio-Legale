<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Avv. Maria Cristina Farinetti</title>

  <style>
    body {
      margin: 0;
      font-family: "Segoe UI", Arial, sans-serif;
      /* grigio chiaro soft, non accecante */
      background: linear-gradient(135deg, #f1f1f1, #e6e6e6);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .card {
      background: #faf9f7; /* panna molto leggera */
      width: 340px;
      padding: 30px 24px 26px;
      border-radius: 16px;
      box-shadow: 0 16px 32px rgba(0,0,0,0.18);
      position: relative;
      overflow: hidden;
      color: #2b2b2b;
    }

    /* motivo geometrico minimal */
    .card::before {
      content: "";
      position: absolute;
      top: -70px;
      right: -70px;
      width: 180px;
      height: 180px;
      border: 1px solid rgba(0,0,0,0.04);
      transform: rotate(45deg);
    }

    h1 {
      margin: 0;
      font-size: 20px;
      font-weight: 600;
      text-align: center;
      letter-spacing: 0.3px;
    }

    h2 {
      margin: 6px 0 26px;
      font-size: 13px;
      font-weight: 400;
      text-align: center;
      color: #6a6a6a;
    }

    .info {
      display: flex;
      gap: 10px;
      margin-bottom: 14px;
      font-size: 14px;
      line-height: 1.4;
    }

    .icon {
      width: 22px;
      text-align: center;
      font-size: 15px;
      color: #7a7a7a;
      flex-shrink: 0;
    }

    .divider {
      height: 1px;
      background: #dedede;
      margin: 22px 0;
    }

    button {
      width: 100%;
      padding: 14px;
      border-radius: 10px;
      border: 1px solid #cfcfcf;
      background: #ededed;
      font-size: 15px;
      font-weight: 500;
      cursor: pointer;
      color: #2b2b2b;
      transition: background 0.2s ease;
    }

    button:hover {
      background: #e2e2e2;
    }
  </style>
</head>

<body>

  <div class="card">

    <h1>Avv. Maria Cristina Farinetti</h1>
    <h2>Studio Legale Farinetti-Ferrero</h2>

    <div class="info">
      <div class="icon">📞</div>
      <div>0173 970312</div>
    </div>

    <div class="info">
      <div class="icon">✉️</div>
      <div>mc.farinetti@gmail.com</div>
    </div>

    <div class="info">
      <div class="icon">📧</div>
      <div>mariacristina.farinetti@ordineavvocatialba.eu</div>
    </div>

    <div class="info">
      <div class="icon">📍</div>
      <div>Via Roma 97/A<br>12043 Canale (CN)</div>
    </div>

    <div class="divider"></div>

    <button onclick="aggiungiContatto()">Aggiungi ai contatti</button>

  </div>

  <script>
    function aggiungiContatto() {
      const vcard = `
BEGIN:VCARD
VERSION:3.0
N:Farinetti;Maria Cristina
FN:Avv. Maria Cristina Farinetti
ORG:Studio Legale Farinetti-Ferrero
TEL;TYPE=WORK,VOICE:0173970312
EMAIL;TYPE=INTERNET:mc.farinetti@gmail.com
EMAIL;TYPE=INTERNET:mariacristina.farinetti@ordineavvocatialba.eu
ADR;TYPE=WORK:;;Via Roma 97/A;Canale;CN;12043;Italia
END:VCARD
      `.trim();

      const blob = new Blob([vcard], { type: "text/vcard" });
      const url = URL.createObjectURL(blob);

      const a = document.createElement("a");
      a.href = url;
      a.download = "Avv_Maria_Cristina_Farinetti.vcf";
      a.click();

      URL.revokeObjectURL(url);
    }
  </script>

</body>
</html>
