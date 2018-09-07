# smartBulbDemo

In the same way Pivotal has been behind Spring projects, providing Java developers with Spring Cloud to help solve the distributed computing problems that came with microservices,  the Steeltoe team started working on the Steeltoe project a couple years ago to provide the same capabilities for .NET developers.
As a .NET developer, you can leverage the same cloud native patterns such as the circuit breaker for preventing cascading failure, service discovery at run time and centralizing application configuration.
Steeltoe also has a library for interacting with the CredHub API to manage credentials such as passwords and certificates. For more information, please visit steeltoe.io.

Demo 1: CredHub client library 

we analyze the strength of the passwords, convert that strength to an RGB color code and send that color code to the smart light bulbs. We also implement the circuit breaker pattern here so if Credhub is not available, then another algorithm will be used to generate the password.

Demo 2: Sentiment analysis 
Anything you say can have a sentiment score. For example, after your hotel stay, when asked to give feedback, if you were to say, “I love the staff and food”, the sentiment score would be 98%. That’s a very positive feedback and we map that score to the color green. If you were to say “I hated the receptionist”, that’s a negative comment, and we get a red light bulb.

Behind the scenes, we called Microsoft Cognitive service to get a sentiment score for the text that we entered. Then we converted the sentiment score to a color code and sent the color code to smart bulbs. Cognitive services requires an API key, that we obviously did not want to store with our source code, so we use Steeltoe Configuration to retrieve that value from a secure location at runtime. 

Demo 3: Twitter connection
Now Let’s do a retro. If you like our demos, tweet with #cfbulbs with all your wonderful compliments, and if you don’t like them, please don’t tweet at all. Of course I’m kidding, we welcome your constructive feedback as well.
what are doing here is getting real time feedback from Twitter - we collect the 10 most recent tweets with our hashtag cfbulbs and send them to Microsoft cognitive service to get sentiment scores. Then we average the scores, convert the score to an RGB color code and send the color code to smart bulbs. We have the service discovery pattern implemented here between the Twitter monitor and the smartbulb web app, of course we also have the config server to store the location of Microsoft cognitive service.

The goal of this demo is for you to see what is possible and that you can do easily as well. 

Here is the github location of the demo. 

When you go back to your office, you are welcome to use our code to play with Steeltoe, or create your own ideas to try out with Steeltoe. Once you get the gist of it, you’ll see how easy it is to use the framework to make your life easier. After you’ve had some fun, you can apply these cloud native patterns to your own .NET applications. Such as centralizing all your app configurations in a config server or implementing circuit breakers around all your integration points in your system.

To sum up, We believe that When you use Steeltoe, you are moving toward a better way of building your applications. You will be able deliver your softwares much faster, and consequently you can leave work on time and get your weekends back. 




