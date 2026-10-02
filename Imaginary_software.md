

All info may be updated whenever necessary. This is to keep generated telemetry consistent


# Servers and their IP addresses and programming languages:

- Always use same IP addresses when requesting data from the same server



## Application servers
- Distributed to two self hosted servers

### Application server programming languages: 
- Python and Javascript (CSS stylesheets for styling frontend)

### Application server IP addresses: 
- 170.57.176.88 (Stockholm)
- 104.172.209.255 (Helsinki)

## User database
- Also on physical hardware
### User database language: 

- PostgreSQL, IP: 88.211.152.184 (Vantaa)

#### Stores: 
- Id, Username, Password, Email

## Message database

Message database language: 

- PostgreSQL, IP: 255.186.179.197 (Uppsala)

Stores: Id, Message, username

## Image service: Cloudinary (May be ignored until later)

## Possibly backup databases

# How the UI would look like?

## Main page address:

address: https://www.nordic_online_discussion_platform.com/

- has search bar for forums and a link to login page and sign up page if you are not logged in
- log out button if you are logged in


## Login page:
https://www.nordic_online_discussion_platform.com/login
 
- link to sing up page and main page

## Sing up page:

https://www.nordic_online_discussion_platform.com/singup

- Link to login page and main page


## Forum pages:

https://www.nordic_online_discussion_platform.com/{forum_name}

- 100 messages per page
- Button to change page

- Button to go back to main page
- log out button



## User actions that generate telemetry (We absolutely do not have to do all of these):
- Load page
- Log in
- Log out
- Search forums
- Send a message 
- Delete message 
- Sing up
- Create forum
- Delete forum
- Send image 
- Delete image

## Crash ideas:

- Page does not load

- Lots of new users overwhelming a server

- can’t load messages for a forum

- Stockholm and Helsinki server can’t communicate


# Some telemetry that can be generated (Person generating telemetry will decide which would be the most important for that action):

Python (Print() etc.):
https://docs.python.org/3/howto/logging.html

PostgreSQL:
https://betterstack.com/community/guides/logging/how-to-start-logging-with-postgresql/

Javascript (console.log() etc.):

https://useful.codes/logging-basics-in-javascript/


## Maybe most important metrics (Can store others as well):

- Page views (Could help detect which page the problem is occuring)
- New visitors ( lots of new accounts are overwhelming service or new people are not joining)
- Returning visitors ( lots of existing accounts are overwhelming service or people have stopped logging in)
- device type( Could tell if issue is mobile or desktop specific)

## traces:

- HTTP requests

- SQL queries

	Not Priority (would be hard to track every function without program): function calls (Python and Javascript functions)






All telemetry should mimic OTLP format because this is what the real data does

# Telemetry for loading Main Page:

## Traces:
- Send HTTP get request to https://www.nordic_online_discussion_platform.com/
- request status 
- Save both the client’s and server’s IP address
## Metrics:
-  update page views for main page (https://www.nordic_online_discussion_platform.com/)
- save device type

## Logs:
- Javascript sends a log message if the CSS file was succesfully loaded
- Javascript sends log message if seach bar couldn't load

