# Reddit Marvel Snap Card Bot
This is a bot for displaying information about Marvel Snap cards on Reddit. It 
operates by monitoring comments as they come through the Marvel Snap subreddit 
(/r/MarvelSnap) and checking each comment for the inclusion of a `[[card_name]]`. 
If something of this form is found, it will reply to the comment with details 
about the requested card, including power, cost, and ability.

This bot creation began when I noticed that the /u/MarvelSnapCardBot had not
posted any card responses in almost a month. From there, I decided to try 
creating a Reddit bot to see what is required for that process.

This bot is intended to mostly provide the same functionality as the original 
/u/MarvelSnapCardBot did, with the following enhancements:
* Open Source! - I was unable to find the previous bots source code to determine how it operated, which resulted in building this from scratch. Many similar Reddit and Discord bots are closed-source, however I want to make this open source to help anyone that may wish to build similar bots or to enhance this bot
* Fuzzy card searching - Cards will not have to be an exact match to work, instead if they are reasonably close enough to an exact match, it will count and display the card. So small typos may occur and the bot will handle it correctly. This is performed by using approximate string matching or "edit distance" between the supplied search term and the actual card name
* No filesystem usage - I'm acheiving this by checking the replies to a comment before commenting on it and checking to see if the bot has already replied to the comment. This is to allow the bot to run in an environment where it does not have access to a persistent filesystem where it may store IDs for comments it has already commented on.

Things still left to do:
* Implement a Docker makefile for running the bot inside of a Docker container
* Investigate Heroku as a hosting service
* Add unit test coverage for components that may be tested (e.g. reddit and Snap API can't really be tested, but other functionality may)
* Obtain approval from /r/MarvelSnap moderators to allow the bot to operate

