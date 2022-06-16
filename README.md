# Recreate a simple Sportsbook Homepage

Starter project in VueJs for Sportsbook Internship, a very simplified version of the Barstool Sportsbook homepage.

![Intern Project Wireframe](./intern-project-2.jpg)

## Starting Project

1. Fork Project into your Github
2. Clone onto your computer
3. `yarn install` in both the root folder and in the server folder.

In root directory run:

`yarn start:ui`

And in a separate terminal tab run:

`yarn start:server`

_Note: The project is already setup so that Axios will have it's base url set to the server, all endpoints should just be used as `/endpoint`_


## Project Outline

What you'll be aiming to do is to:

1. Create a header which lists out the sports returned from the `/all-sports` endpoint.
2. Create a sidebar with 5 items of your choice - either navigation between pages or a list of sports. Each of these items will have an icon which you can find at [https://fonts.google.com/icons](https://fonts.google.com/icons)
3. Create a main section which will:
  + Have rows of events by Sport
  + Each row will have a series of events
  + Each event will have 2 participants with two buttons each (4 in each event box) displaying their lineage
  + On click this button will submit the specific bet

## What We'll Be Looking For

1. Follow the Sportsbook Style Guide
2. Clean, readable, testable, and concise code
3. How you handle input on your PRs, and your communication while in pair programming
4. Ability to find answers, and able to reach out for help when needed

## Endpoints

`/all-sports` - returns all sports

`/events` - events with participant ids and betIds for participants

`/bets` - bets with id and lineage

`/teams` - teams with names and ids

`/sports` - sports with name, key, and eventIds for sports



