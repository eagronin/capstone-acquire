# Introduction



# Description of Catch The Pink Flamingo Online Game
One of the products of an imaginary company Eglence Inc. is a highly popular mobile game called “Catch The Pink Flamingo”. The objective of the game is to catch as many Pink Flamingos as possible by following the missions provided by real-time prompts in the game and cover the map provided for each level. The levels get more complicated in mission speed and map complexity as the users move from level to level.

It’s a multi-user game where the players have to catch Pink Flamingos that randomly pop up on a gridded world map based on missions that change in real-time. For the player or team to move to the next complexity level, they need to have at least one point in every map grid cell, i.e., cover the whole world map. An example mission would be “Catch the Flamingos on land with stars on their belly” in which the player should only click on flamingos that match the mission criteria, in this case, stars and being on land. If the player tags any other flamingo on the map, he/she or his/her team gets a negative point (-1) on that map location.

After the initial sign up, a player (user) is asked to play the Level 1 individually without joining any team. This is where the user gets trained as a player and starts building a game history. Level 1 is an easy entry to the game composed of only 64 (8x8) grid cells and longer, more obvious, fun missions. Upon completion of Level 1, the player gets asked if she/he wants to join any team or form a team and will continue the rest of the time as a team player even if that means the user is a 1-person team of her/his own.

At the beginning of each level, the game creates a brand new map with more cells than the level before. The complexity of the missions also increases. The missions change more frequently as the levels increase.

The players keep in touch via chat boards assigned to the teams and also via social media, e.g., Twitter.

There are some things to consider while designing an information system for this game:

- Ranking of Users: Each user will be ranked individually by the speed and accuracy of their click to completion. The rankings get tracked in real-time and can be viewed both via the mobile app and the website for the game. In addition to score, speed and accuracy based ranking, the other players can see what parts of the map the user has the most points for. The players are also categorized based on their history as “rising star”, “veteran”, “coach”, “social butterfly” and “hot flamingo”. These refer to the qualities of players in addition to the game statistics.
- Ranking of Teams: The teams are ranked publicly. There is a maximum of 30 members in a team and a minimum of 1 member. The players “ask” to join a team and get voted in when 80% of the team members allow. A team may choose to “recruit” if they think a player can contribute or “outvote” a player if a player is not contributing. The players are also allowed to change their teams and bring all their points along. The competition is built on “point-based economy” and it is encouraged by the game providers. When all players leave a team, the team automatically gets removed from public and archived by Eglence Inc.
- In-game Purchases: Users are allowed in game purchases including binoculars to spot the mission specific flamingos, special flamingos that count for more than one grid point, ice blocks to freeze a mission for 20 seconds when needed, and trading cards to transfer the extra points from some grid cells to the ones without any points.
- Game Completion: The game never ends, meaning that there will always be a more complicated next level. A challenge for Eglence Inc. is to keep the game interesting and engaging for players who have been around for a long time. They make use of big data analytics to make sure the veteran players are still around.

# Data Set Overview

 File Name	| Description	| Fields 
|:--- | :--- |:--- |
 ad-clicks.csv | A line is added to this file when a player clicks on an advertisement in the Flamingo app. | timestamp: when the click occurred. <br/><br/>txId: a unique id (within ad-clicks.log) for the click. <br/><br/>userSessionid: the id of the user <br/><br/>session for the user who made the click.  <br/><br/>teamid: the current team id of the user who made the click.  <br/><br/>userid: the user id of the user who made the click. <br/><br/>adId: the id of the ad clicked on. <br/><br/>adCategory: the category/type of ad clicked on.
buy-clicks.csv	| A line is added to this file when a player makes an in-app purchase in the Flamingo app.	| timestamp: when the purchase was made. <br/><br/>txId: a unique id (within buy-clicks.log) for the purchase. <br/><br/>userSessionId: the id of the user session for the user who made the purchase. <br/><br/>team: the current team id of the user who made the purchase. <br/><br/>userId: the user id of the user who made the purchase. <br/><br/>buyId: the id of the item purchased. <br/><br/>price: the price of the item purchased.
users.csv | This file contains a line for each user playing the game. |	timestamp: when user first played the game. <br/><br/>userId: the user id assigned to the user. <br/><br/>nick: the nickname chosen by the user. <br/><br/>twitter: the twitter handle of the user. <br/><br/>dob: the date of birth of the user. <br/><br/>country: the two-letter country code where the user lives.
team.csv	| This file contains a line for each team terminated in the game.	| teamId: the id of the team <br/><br/>name: the name of the team. <br/><br/>teamCreationTime: the timestamp when the team was created. <br/><br/>teamEndTime: the timestamp when the last member left the team. <br/><br/>strength: a measure of team strength, roughly corresponding to the success of a team. <br/><br/>currentLevel: the current level of the team.
team-assignments.csv	| A line is added to this file each time a user joins a team. A user can be in at most a single team at a time.	| timestamp: when the user joined the team. <br/><br/>team: the id of the team. <br/><br/>userId: the id of the user. <br/><br/>assignmentId: a unique id for this assignment.
level-events.csv	| A line is added to this file each time a team starts or finishes a level in the game	| timestamp: when the event occurred. <br/><br/>eventId: a unique id for the event. <br/><br/>teamId: the id of the team. <br/><br/>teamLevel: the level started or completed. <br/><br/>eventType: the type of event, either start or end.
user-session.csv | Each line in this file describes a user session, which denotes when a user starts and stops playing the game. Additionally, when a team goes to the next level in the game, the session is ended for each user in the team and a new one started. | timestamp: a timestamp denoting when the event occurred. <br/><br/>userSessionId: a unique id for the session. <br/><br/>userId: the current user's ID. <br/><br/>teamId: the current user's team. <br/><br/>assignmentId: the team assignment id for the user to the team. <br/><br/>sessionType: whether the event is the start or end of a session. <br/><br/>teamLevel: the level of the team during this session. <br/><br/>platformType: the type of platform of the user during this session. 
game-clicks.csv	| A line is added to this file each time a user performs a click in the game. |	timestamp: when the click occurred. <br/><br/>clickId: a unique id for the click. <br/><br/>userId: the id of the user performing the click. <br/><br/>userSessionId: the id of the session of the user when the click is performed. <br/><br/>isHit: denotes if the click was on a flamingo (value is 1) or missed the flamingo (value is 0). <br/><br/>teamId: the id of the team of the user. <br/><br/>teamLevel: the current level of the team of the user.
		
		
		
		
		
		
		
		
		
				
		
		
		
		
		
