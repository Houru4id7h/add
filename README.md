const express = require("express")
const app = express();
var listener = app.listen(process.env.PORT || 2000, function () {
  console.log('Your app is listening on port ' + listener.address().port);
});
app.listen(() => console.log("I'm Ready To Work..! 24H"));
app.get('/', (req, res) => {
  res.send(`
  <body>
  <center><h1>Bot 24H ON!</h1></center
  </body>`)
});
const Discord = require('discord.js');
const client = new Discord.Client();

let coins = 1000;
let fruits = [];

client.on('message', message => {
  if (message.content.startsWith('!')) {
    const args = message.content.slice(1).trim().split(/ +/);
    const command = args.shift().toLowerCase();

    if (command === 'راتب') {
      const amount = Math.floor(Math.random() * (1000 - 300 + 1)) + 300;
      coins += amount;
      message.reply(`تم إضافة ${amount} كوينز لرصيدك.`);
    } else if (command === 'random') {
      const fruitOptions = ['Ice', 'Sand', 'Dark', 'Diamond', 'Light', 'Rubber', 'Barrier', 'Ghost', 'Magma', 'Quake', 'Buddha', 'Love', 'Spider', 'Sound', 'Phoenix', 'Portal', 'Rumble', 'Pain', 'Blizzard', 'Gravity', 'Mammoth', 'T-Rex'];
      const randomFruit = fruitOptions[Math.floor(Math.random() * fruitOptions.length)];
      coins -= 300;
      fruits.push(randomFruit);
      message.reply(`تم خصم 300 كوينز من رصيدك. الفاكهة العشوائية هي: ${randomFruit}`);
    } else if (command === 'fruits') {
      const fruit = fruits.pop();
      message.reply(`الفاكهة في محفظتك هي: ${fruit} وعددها ${fruits.length + 1}`);
    } else if (command === 'coins') {
      message.reply(`عدد الكوينز في رصيدك هو: ${coins}`);
    }
  }
});

client.login(MTIzNjAxMjY0NTg1ODE1MjQ2OQ.GaLeIC.l22qTnDCFZrwMRUjKpk-yan5ewaAgsDyKRmS1Y);
