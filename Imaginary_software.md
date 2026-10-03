

All info may be updated whenever necessary. This is to keep generated telemetry consistent

**Looking at guides and documentation for how both real and fake telemetry is collected and should look like will likely help you with figuring out how the fake telemetry should look like better than this documentation alone!**


# Servers and their IP addresses and programming languages:

- All Servers use Linux (Ubuntu), in case we are tracking system logs

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


# Some telemetry that can be generated :
Person generating telemetry for specific scenario will decide which would be the most important 
## Logs

Logs: "Why did this specific thing happen?" (detailed context and events)

In context of telemetry, the whole context of a specific custom event. Often includes traces as context. (For example log in event could include both HTTP request and database query as context)


Log could also refer to the more familiar logs, that is usually just the custom message sent to the console. Thought these can also be stored as telemetry
Python (Print() etc.):
https://docs.python.org/3/howto/logging.html

PostgreSQL:
https://betterstack.com/community/guides/logging/how-to-start-logging-with-postgresql/

Javascript (console.log() etc.):

https://useful.codes/logging-basics-in-javascript/


## Maybe most important metrics (Can store others as well):
Metrics: "What is happening across all requests?" (aggregated statistics)

- Page views (Could help detect which page the problem is occuring)
- New visitors ( lots of new accounts are overwhelming service or new people are not joining)
- Returning visitors ( lots of existing accounts are overwhelming service or people have stopped logging in)
- device type( Could tell if issue is mobile or desktop specific)

## traces:
Traces: "What happened during this specific request?" (individual request lifecycle)

In context of telemetry, refers to a specific request, query or function

- HTTP requests

- SQL queries

	Not Priority (would be hard to track every function without program): function calls (Python and Javascript functions)





**Would be good if all Telemetry would mimic OTLP format**

Traces, metrics and logs should likely be saved in different places?


- Would be good if the log included trace_id to the related HTTP request trace


