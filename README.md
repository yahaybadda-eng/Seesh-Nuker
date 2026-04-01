const { Client, GatewayIntentBits } = require('discord.js');

const client = new Client({
  intents: [GatewayIntentBits.Guilds, GatewayIntentBits.GuildMessages, GatewayIntentBits.MessageContent]
});

client.once('ready', () => {
  console.log(`✅ Logged in as ${client.user.tag}`);
});

// أمر ping
client.on('messageCreate', message => {
  if (message.content === '!ping') {
    message.reply('🏓 Pong!');
  }
});

// أمر معلومات
client.on('messageCreate', message => {
  if (message.content === '!info') {
    message.reply(`📌 اسمك: ${message.author.username}`);
  }
});

client.login('TOKEN_HERE');
