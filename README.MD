# UnScrew
UnScrew is a Kik Unbricker that uses [Tomer8007's Kik Bot API](https://github.com/tomer8007/kik-bot-api-unofficial) to acknowledge ("ack") message history that would otherwise brick an account on a normal smartphone client, similar to Rayg's Unbricker, ["Unbrik"](https://unbrik.ragebot.net/). The key difference is that instead of loading and acking all history, Unscrew starts by only loading the JID of each item, ignoring the contents if the JID has been flagged. If a JID is not flagged, the item contents are checked for spam (duplicate contents) and known exploits, if any are found, the sender's JID is flagged. In addition, UnScrew does the same for present traffic as well, and continues to unbrick until you sign back in, or until 15 minutes has passed. This makes the process more effective against modern exploits and spam!


# Usage
To unbrick an account, go to [UnScrew.Online](https://unscrew.online/) and select "Online tool", then enter your username and password and select submit. 

Alternatively, you can send a POST request to UnScrew's API via your shell or in a script of your own! Formatting for the POST request is:

`curl -X POST -d userAndPass=<USERNAME:PASSWORD> https://unscrew.online`

The possible results are as follows:

- **"Success"** - UnScrew successfully logged in and is unbricking your account.


- **"Incorrect credentials"** - The username or password you sent is incorrect.


- **"Incorrect formatting"** - The input you gave for userAndPass was not formatted correctly.


- **"Captcha"** - There is a captcha on the account that must be manually cleared before UnScrew can continue.


- **"Connection failed"** - Kik is refusing or closing the connection. This means Kik is down or your account is shadow banned.


- **"Something went wrong"** - UnScrew ran into an internal error, contact Stetho if you encounter this!


- **"Under maintenance"** - UnScrew is down for maintenance, try again later!


- **"Blocked"** - You're sending requests too fast and activated antispam, slow down!


- **"Blacklisted"** - You have been blacklisted from using the UnScrew API. 

# Thank you!
A huge thank you goes out to UnScrew's [contributors](https://unscrew.online/credits/)! As I obtain more information on the latest exploits, I'll be updating logs and creating result pages on the website to show more information about what exploits were detected, who created them, and how to defend against them on your own. Though I have a decent amount of data to work with as of right now, new exploits are always being discovered! If you have information regarding exploits that you're willing/able to contribute to improve UnScrew, or if you have suggestions to improve the website/API, please [contact me](https://kik.me/u/stetho)!
