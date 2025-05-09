# Mlbb-info-tools
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>MLBB Info Tools</title>
  <style>
    body { font-family: Arial, sans-serif; background: #111; color: #eee; padding: 20px; }
    input, textarea, button { width: 100%; margin-top: 10px; padding: 8px; font-size: 14px; }
    .output-box { white-space: pre-wrap; background: #222; padding: 10px; border-radius: 5px; margin-top: 20px; }
  </style>
</head>
<body>
  <h2>MLBB Info Tools</h2>
  
  <label>ID:</label>
  <input type="text" id="id">
  
  <label>Server:</label>
  <input type="text" id="server">
  
  <label>Nickname:</label>
  <input type="text" id="nickname">
  
  <label>Total Hero:</label>
  <input type="number" id="hero">
  
  <label>Total Skin:</label>
  <input type="number" id="skin">
  
  <label>Last Login (dd-mm-yyyy hh:mm:ss):</label>
  <input type="text" id="lastlogin">
  
  <label>Player MMR:</label>
  <input type="text" id="mmr">
  
  <label>Last Login Country:</label>
  <input type="text" id="logincountry">
  
  <label>Create Role Country:</label>
  <input type="text" id="rolecountry">
  
  <label>Create Account Date:</label>
  <input type="text" id="createdate">
  
  <label>Moonton Email:</label>
  <input type="text" id="moonton">
  
  <label>Google Play Email:</label>
  <input type="text" id="google">
  
  <label>Facebook Email:</label>
  <input type="text" id="facebook">
  
  <button onclick="generate()">Buat Detail</button>
  <button onclick="saveTxt()">Simpan ke .txt</button>
  
  <div class="output-box" id="output"></div>

  <script>
    function generate() {
      const get = id => document.getElementById(id).value;
      const out = `✧ ID: ${get("id")}
✧ Server: ${get("server")}
✧ Nickname: ${get("nickname")}
✧ Total Hero: ${get("hero")}
✧ Total Skin: ${get("skin")}
✧ Last Login: ${get("lastlogin")}
✧ Player MMR: ${get("mmr")}
✧ Last Login Country: ${get("logincountry")}
✧ Create Role Country: ${get("rolecountry")}
✧ Create Account: ${get("createdate")}
———————————————
BIND ACCOUNT INFO:
✧ Moonton : ${get("moonton")}
✧ Google Play : ${get("google")}
✧ Facebook : ${get("facebook")}`;

      document.getElementById("output").innerText = out;
    }

    function saveTxt() {
      const text = document.getElementById("output").innerText;
      const blob = new Blob([text], {type: "text/plain"});
      const link = document.createElement("a");
      link.href = URL.createObjectURL(blob);
      link.download = "DetailAkunMLBB.txt";
      link.click();
    }
  </script>
</body>
</html>
