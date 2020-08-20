This study guide should reinforce and provide practice for all of the concepts you have seen in the past week. It consists of written questions and coding exercises, both are equally important to prepare you for the sprint challenge as well as to be able to speak on these topics comfortably in interviews and on the job.

If you get stuck or are unsure of something remember the 20 minute rule. If that doesn't help, then research a solution with [Google](https://www.google.com) and [StackOverflow](https://www.stackoverflow.com). Only once you have exausted these methods should you turn to your Team Lead - they won't be there on your SC, or during an interview. That being said, don't hesitate to ask for help if you truly are stuck.

Have fun studying!

# Questions of Understanding
1. Define the following and give an example of an appropriate task for each:
	- Front-end: The front-end is everything with which the user interacts.
	- Back-end: The back-end includes functions and data processing behind the scenes.
	- Database: A databse is a data structure that stores organized information.

2. What is a decorator?
- A decorator is a design pattern that allows behavior to be added to an individual object whitout affecting the behavior of other objects from the same class

3. What is a route?
- A mechanism where HTTp requests are routed to the code that handles them, or what should happen when a user visits a certain page.

4. Why do we want to separate our code into separate files when writing an application? Why not just one big file?
- Splitting the code into separate files allows parts of an application to be worked on without having to worry about what else is going on in the program. 

5. What is an API? Give an example of an API that is not Twitter's.
- API stands for Application Programming Interface, and it allows to applications to talk to each other. Browsing Facebook on your phone, checking the weather on your computer, that's when you're using an API.

6. What does it mean to pickle a model? Why might this be useful?
- Pickling converts a Python object so it can be stored in a file or database, maintains program state across sessions, and/or transport data over a network.

# Basics of Flask

## Coding
Write a Flask application that displays "Hello World!" to the local host (usually `127.0.0.1:5000` or `localhost:5000`)

## Questions of Understanding
1. Flask is described as a "microframework" for developing web applications. What is a "microframework"?
- Microframeworks are minimalistic web applications that aim to keep the core of an application simple but extensible.

2. What is another web development framework in Python?
- Django

3. In this line of code: `APP = Flask(__name__)` What does `__name__` do?
- It is a built in variable that evaluates the name of the current module.

4. What line of your code tells when and where "Hello World!" should be displayed?
- @app.route

5. What do we need to type into the terminal to run our flask application?
- FLASK_APP=hello.py

# API's

## Coding
API's are a common part of programming, whether setting up your own or using someone else's. Today we will be looking at the API for the board gaming hobby site BoardGameGeek (BGG). The API instructions can be found [here](https://boardgamegeek.com/wiki/page/BGG_XML_API&redirectedfrom=XML_API#). There are many wrappers online for the BGG API that you may use but the sample code below will use `requests` and the web scraping library `BeautifulSoup`.

```python
import requests
import bs4

game_id = 13
url = 'https://www.boardgamegeek.com/xmlapi/boardgame/' + str(game_id)
result = requests.get(url)
soup = bs4.BeautifulSoup(result.text, features='lxml')

print(soup.find('name').text)
```

The code above uses the API to search for a game by its ID number (more than 16,000 entries on BGG). Once the API returns the results, BeautifulSoup is used to parse the XML and make it easily searchable.

Explore the BGG API and see if you are able to find the following information about a game:

* Name - Catan
* Max and Min Players - 
* Play Time
* Game Description - In Catan (formerly The Settlers of Catan), players try to be the dominant force on the island of Catan by building settlements, cities, and roads. On each turn dice are rolled to determine what resources the island produces. Players collect these resources (cards): wood, grain, brick, sheep, or stone to build up their civilizations to get to 10 victory points and win the game. Setup includes randomly placing large hexagonal tiles (each showing a resource or the desert) in a honeycomb shape and surrounding them with water tiles, some of which contain ports of exchange. Number disks, which will correspond to die rolls (two 6-sided dice are used), are placed on each resource tile. Each player is given two settlements (think: houses) and roads (sticks) which are, in turn, placed on intersections and borders of the resource tiles. Players collect a hand of resource cards based on which hex tiles their last-placed house is adjacent to. A robber pawn is placed on the desert tile. A turn consists of possibly playing a development card, rolling the dice, everyone (perhaps) collecting resource cards based on the roll and position of houses (or upgraded cities&mdash;think: hotels) unless a 7 is rolled, turning in resource cards (if possible and desired) for improvements, trading cards at a port, and trading resource cards with other players. If a 7 is rolled, the active player moves the robber to a new hex tile and steals resource cards from other players who have built structures adjacent to that tile.<br/><br/>Points are accumulated by building settlements and cities, having the longest road and the largest army (from some of the development cards), and gathering certain development cards that simply award victory points. When a player has gathered 10 points (some of which may be held in secret), he announces his total and claims the win.<br/><br/>Catan has won multiple awards and is one of the most popular games in recent history due to its amazing ability to appeal to experienced gamers as well as those new to the hobby.<br/><br/>Die Siedler von Catan was originally published by KOSMOS and has gone through multiple editions. It was licensed by Mayfair and has undergone four editions as The Settlers of Catan. In 2015, it was formally renamed Catan to better represent itself as the core and base game of the Catan series. It has been re-published in two travel editions, portable edition and compact edition, as a special gallery edition (replaced in 2009 with a family edition), as an anniversary wooden edition, as a deluxe 3D collector's edition, in the basic Simply Catan, as a beginner version, and with an entirely new theme in Japan and Asia as Settlers of Catan: Rockman Edition. Numerous spin-offs and expansions have also been made for the game.
* Some of the game mechanics

# Flask and Databases

## Code
Write a Flask web application using `SQLAlchemy` with the following:
- [ ] A home route that displays at least one entry from a database of stored BGG game information

  

- [ ] A dynamic route `/add/<game_id>` that adds game information into your database based on the ID in the route.

  

- [ ] A route that resets the database

  

- [ ] The database should have the following following columns as a minimum: id (integer), name (string), and max_players (integer)

## Questions of Understanding
1. What line of code establishes what database should be used for your application?

   

2. How do we define our table, what columns are going to be in it, and what those column datatypes are?

   

3. How do we make a query to our database?

# HTML Templates

## Code
- [ ] Create a small HTML template to display all the games in your database. Update your home route to use this template.

## Questions of Understanding
1. What is an HTML template?

   

2. What module do we need to import from `flask` to use our HTML template?

# Heroku

## Code
It is not necessary, but you can try putting your application on Heroku.

## Questions of Understanding
1. What is a platform-as-a-service?

   

2. Why do we need to use a service like Heroku? Why not just host the application on our local machine?
