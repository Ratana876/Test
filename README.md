<!DOCTYPE html>
<html lang="km">
<head>
<meta charset="UTF-8">
<title>KH Top-Up Diamonds</title>
<style>
body {
    font-family: Arial, 'Khmer OS', sans-serif;
    background: #0f172a;
    color: #fff;
}
.container {
    max-width: 420px;
    margin: 30px auto;
    background: #020617;
    padding: 20px;
    border-radius: 12px;
}
h1 {
    text-align: center;
    color: #38bdf8;
}
label {
    margin-top: 10px;
    display: block;
}
input, select {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    border-radius: 6px;
    border: none;
}
button {
    width: 100%;
    margin-top: 15px;
    padding: 12px;
    background: #38bdf8;
    border: none;
    border-radius: 8px;
    font-size: 16px;
    cursor: pointer;
}
button:hover {
    background: #0ea5e9;
}
small {
    color: #94a3b8;
}
</style>
</head>
<body>

<div class="container">
<h1>💎 KH Top-Up Diamonds</h1>

<label>🎮 ហ្គេម</label>
<select id="game">
    <option>Mobile Legends</option>
    <option>Free Fire</option>
</select>

<label>🆔 Player ID</label>
<input id="player" placeholder="12345678 (4321)">

<label>💎 Diamonds</label>
<select id="diamond">
    <option>86 Diamonds</option>
    <option>172 Diamonds</option>
    <option>257 Diamonds</option>
    <option>344 Diamonds</option>
</select>

<label>📱 Telegram / Phone</label>
<input id="contact" placeholder="@username / 0xxx">

<button onclick="sendOrder()">🛒 បញ្ជាទិញឥឡូវនេះ</button>

<br><br>
<small>
❌ មិនសុំ Password <br>
✅ Top-Up តាម Player ID ប៉ុណ្ណោះ
</small>
</div>

<script>
const BOT_TOKEN = "PUT_YOUR_BOT_TOKEN";
const CHAT_ID = "PUT_YOUR_CHAT_ID";

function sendOrder() {
    const game = document.getElementById("game").value;
    const player = document.getElementById("player").value;
    const diamond = document.getElementById("diamond").value;
    const contact = document.getElementById("contact").value;

    const text =
`🛒 ORDER NEW
🎮 Game: ${game}
💎 Diamonds: ${diamond}
🆔 ID: ${player}
📱 Contact: ${contact}`;

    fetch(`https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`, {
        method: "POST",
        headers: {"Content-Type": "application/json"},
        body: JSON.stringify({
            chat_id: CHAT_ID,
            text: text
        })
    })
    .then(() => alert("✅ បានផ្ញើបញ្ជាទិញរួច! សូមទាក់ទង Admin"))
    .catch(() => alert("❌ មានបញ្ហា"));
}
</script>

</body>
</html>
