## How to make a Discord bot

This guide will take you through making a Discord bot which you can interact with. This is a guide for complete beginners. If you are familiar with JS(JavaScript) and/or Discord.JS, this guide is not for you.


```diff
- 1: Requirements and Downloads
```



The requirements and downloads to make a simple Discord bot are very simple. If you already have this done, you can skip this below:
* A discord Developer Portal application
^^ https://discord.com/developers/applications > New Application > Create
This will create a new application which is crucial for the next step.
* A bot created inside that Developer Portal application
^^ https://discord.com/developers/applications/(PUTYOURAPPIDHERE)/information > Bot > Add Bot
This will add a new Bot to your already existing application.
* A good text editor (optional but recommended for understanding the code better)
^^ I use Sublime Text 3 (free without registration) or Visual Studio Code (free and very good but resource-heavy to small computers)


* Install Node.js

And that is pretty much all for the requirements and downloads.


```diff
- 2: Getting started
```


In this section we will start using NPM to install discord.js and writing some code.
For this section I will be going through Visual Studio Code to help you out. You will also need an IDE of your choice to run the code (VSC comes built-in)

First, create a new file on your Desktop named "My Bot". Go into Visual Studio Code and click "Open new folder" and find that file, open it, then select this folder.

Navigate to the Terminal tab at the top and press new terminal. Wait for the terminal to finish loading (should be at the bottom of your screen) and then type in it `npm init`. Assuming you downloaded everything correctly, some dialogue inputs should pop up. Basically you can just press `Enter` on everything until it says "Is this OK?". Type "yes". At the end it will create the file. If you at any time want to exit out of this menu, you can press (on Windows) `ctrl + c`. After it is done loading, type `npm i discord.js@11.5.1`. This will install the version 11 of Discord.js. You can use V12 but you will need to check the Discord.js documentation to update my code here so it will fit your code. After it is done, re-open VSC so the files show.

Make a new file and name it `index.js`.
On the first line, you will console.log to test if you set up everything correctly.
```js
console.log("Hello, world! My code is running correctly.")
```
Head on back to the terminal and run `node index.js`. If all goes correctly, it should say somewhere "Hello, world! My code is running correctly."

Delete all of the code you jsut wrote and replace it with this block of code:
```js
const Discord = require('discord.js');
const client = new Discord.Client();
var token = 'PUT_YOUR_BOT_HIDDEN_TOKEN_HERE'

client.on('ready', () => {
  console.log(`Logged in as ${client.user.tag}!`);
});

client.on('message', msg => {
  if (msg.content === '!ping') {
    msg.reply('Pong!');
  }
});

client.login(token);
```
Let's go through what this code does. This was taken off of the official Discord.js website and modified a bit. The first line of code declares the Discord.js library in a variable so we can call it later. The second line makes a new client inside of Discord.js (not logged in yet). The third line of code you need to replace inside of the quotes with your bot's hidden token. You can do this by going over to your developer portal, going to your Application, then going to bot. It should be there. The next 3 lines are inside of an event. This event fires (or runs the code inside of it) whenever the client (your bot instance) is ready. The next event down from that detects a message. It detects "!ping" and outputs "Pong!". The last line of code will make your bot login. This should always be at the end of your code. Save your code with Ctrl + S and then go back to the terminal. In the terminal, write `node index.js` again. If you did everything correctly, you should get a message in the console (terminal) saying "Logged in as (Numbers are here)". This means your bot is ready to be used. Now, how do I use it you ask? Well, you need to invite it first!


```diff
- 3: Inviting your bot
```

Inviting your bot is not difficult at all. You just need to know your permission integers or use a calculator (which discord provides for you). Go over to your application and into bot. Scroll all the way down and you should see a black box. This is a permission integer calculator. Discord's permissions are not stored as strings like 'MANAGE_MESSAGES', but are stored as integers or numbers. 8 is admin, and it's pretty much all you should need for an advanced bot, but for now click 'Manage Messages' and copy the output it gives you at the bottom.

This is where things get a bit confusing, so hang on tight. What you want to do is open a new tab and have it ready to paste a URL into. Put this into the URL **and do not press enter yet**: https://discord.com/oauth2/authorize?client_id=YOURBOTCLIENTIDHERE&scope=bot&permissions=YOURPERMISSIONINTEGERHERE

You need to fill out two things in that link. Do you see "YOURBOTCLIENTIDHERE"? Go back to your app and copy the Client ID and replace it with that. Do you see "YOURPERMISSIONINTEGERHERE"? Go back to the permission calculator and copy the number it gave you. Replace it with that. Now, you may press `Enter`. It should bring you to a page and if you have the correct permissions, you can invite the bot. It's good to invite the bot to a testing server first.


```diff
- 4: Using your bot
```

Once you have invited your bot, go to a channel the bot can see and type "!ping". Watch the magic happen, and...

```diff
- 5: Congratulations!
```

You now just made your first bot. I recommend checking out other more advanced tutorials if you want your bot to do more like kick or ban members and a lot more. This journey will be super fun, and I wish the best of luck to you!









# Thank you for reading. Made by Voidus_k#8707 on Discord. Resources are located in the files of this GitHub.