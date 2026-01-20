# Repositorios-de-telegram
Cómo crear un de telegram 
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Sergio Bot - Documentación</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #0f172a;
      color: #e5e7eb;
    }
    header {
      background: #020617;
      padding: 20px;
      text-align: center;
      border-bottom: 1px solid #1e293b;
    }
    header h1 {
      margin: 0;
      color: #38bdf8;
    }
    main {
      max-width: 900px;
      margin: auto;
      padding: 20px;
    }
    section {
      margin-bottom: 40px;
      background: #020617;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.4);
    }
    h2 {
      color: #38bdf8;
      border-bottom: 1px solid #1e293b;
      padding-bottom: 5px;
    }
    pre {
      background: #020617;
      border: 1px solid #1e293b;
      padding: 15px;
      border-radius: 8px;
      overflow-x: auto;
      color: #a5f3fc;
    }
    code {
      color: #a5f3fc;
    }
    ul li {
      margin-bottom: 6px;
    }
    footer {
      text-align: center;
      padding: 20px;
      color: #64748b;
      border-top: 1px solid #1e293b;
    }
  </style>
</head>
<body>

<header>
  <h1>🤖 Sergio Bot - Telegram</h1>
  <p>Documentación oficial del proyecto</p>
</header>

<main>

<section>
  <h2>📦 Requisitos</h2>
  <ul>
    <li>Termux</li>
    <li>Node.js</li>
    <li>Cuenta de Telegram</li>
    <li>Un bot creado con @BotFather</li>
  </ul>
</section>

<section>
  <h2>🛠️ Instalación en Termux</h2>
  <pre><code>pkg update && pkg upgrade
pkg install nodejs git</code></pre>
</section>
<pre><code>
node -v
  </code></pre>
</section>
<pre><code>
npm -v
  </code></pre>
</section>
<pre><code>
mkdir telegram-bot
cd telegram-bot
  </code></pre>
</section>
<pre><code>
npm init -y
  </code></pre>
</section>
<pre><code>
npm install node-telegram-bot-api
nano index.js</code></pre>
</section>

<section>
  <h2>🧠 Código del Bot (index.js)</h2>
  <pre><code>const TelegramBot = require("node-telegram-bot-api");

const TOKEN = "AQUI_VA_TU_TOKEN";
const bot = new TelegramBot(TOKEN, { polling: true });

console.log("🤖 Sergio Bot encendido y listo");

bot.on("message", (msg) => {
  const chatId = msg.chat.id;
  const text = msg.text;
  const pushName = msg.from.first_name || "Usuario";

  if (!text) return;

  if (text === "/menu") {
    const imageUrl = "https://i.imgur.com/tuImagen.jpg";
    const caption = `
♣*𝑺𝒆𝒓𝒈𝒊𝒐 𝑩𝒐𝒕*🌉
╭─────────────────╮
┊ Usuario: *${pushName}*
┊ /start
┊ /ping
┊ /menu
┊ /info
┊ /hola
╰─────────────────╯
    `;
    bot.sendPhoto(chatId, imageUrl, { caption, parse_mode: "Markdown" });
    return;
  }

  if (text === "/start") {
    bot.sendMessage(chatId, `Hola 👋 ${pushName}, escribe /menu`);
    return;
  }

  if (text === "/ping") {
    bot.sendMessage(chatId, "pong 🏓");
    return;
  }

  if (text === "/info") {
    bot.sendMessage(chatId, "🤖 Sergio Bot v1.0");
    return;
  }

  if (text === "/hola") {
    bot.sendMessage(chatId, "Hola 😎");
    return;
  }

  bot.sendMessage(chatId, "❌ Comando no reconocido. Usa /menu");
});</code></pre>
</section>

<section>
  <h2>▶️ Ejecutar el Bot</h2>
  <pre><code>node index.js</code></pre>
  <p>Si todo va bien verás:</p>
  <pre><code>🤖 Sergio Bot encendido y listo</code></pre>
</section>

<section>
  <h2>📌 Comandos Disponibles</h2>
  <ul>
    <li>/start</li>
    <li>/menu</li>
    <li>/ping</li>
    <li>/info</li>
    <li>/hola</li>
  </ul>
</section>

<section>
  <h2>🔐 Seguridad</h2>
  <p>No subas tu token real a GitHub. Si lo haces, luego no llores cuando te roben el bot.</p>
</section>

</main>

<footer>
  <p>© Sergio Bot Project - Documentación</p>
</footer>

</body>
</html>
