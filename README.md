# Setup

Simply clone the repo and run `yarn serve`

# Mentally Friendly Notes/Journal

##### <ins>Descisions and Planning</ins> - 30/07/2019 0830 - https://trello.com/c/cZteem1z & https://trello.com/c/03a70wZ1

On top of the documentation and trello board I've decided to write a journal for a verbose experience of my thoughts and proDecisionscess's throughout this projects life cycle. 

I recieved the design brief yesterday and have had the luxury of 24 hours to think about how I'm going to approach this project. 

###### Technologies

* Git/Github/Git-Flow - Will utilise the git-flow working off the `, once the project is done do `. Use GitHub to display the code and place this as the README.md
* Vue.js/Vue-CLI - Utilise Vue.js as the frontend framework following its design guide and principles, also use Vue-CLI for tooling and project layout
* Trello/Markdown - Use trello as a high level task/feature list, utilise time-estimation within cards. For all other notes and docuumentaton use markdown.
* BootstrapVue - utilise bootstrap-vue for css https://bootstrap-vue.js.org/
* 

###### Decisions

* Minimise the use of external liabries - make the code as vinalla Vue.js as possible
* Make the site responsive to widths
* Incorperate some basic testing of the project
* Make it [Zen](https://nicoledominguez.com/assets/public/zen-py.png) - although this isn't a python project I belive these are great points to guide me along the path
* ES6 standards

My main goal is to complete the two sorting stories provided in the design brief. To get there I'm going to create some basic stories outlining what I need to do to get to that point. 

I've set up trello with 3 lists; `Todo`: tasks that are in the backlog, `Doing`: currently in progress and `Done`: things that have been completed also will place an actual time spent at this point to identify and discrepencies in my estimates.

> 1 point = 30 minute

I finished this at about 10am - in total I spent 1.5 hours

##### <ins>Skeleton</ins> - 30/07/2019 1130 - https://trello.com/c/7RPuPxRo

Intially I set up all the nesseary plugins and tools outlined above. 

* Created a main component to encapuslate a show - this way if the json is extended to more shows we can reuse this component rather than creating a new one for each show
  * With in this component currently there are two other components Summary and Episode - I'll probably create another for the Episode card
  * `Summary.vue`simply contains the summary of the series
  * `Episodes.vue` contains all the sorting and display code for the episodes guide.
* Currently I've loaded the json file as part of the entire App scope - I may change this to sort the data and then prop up each component with there nessecary data - bit for now I just want to get the data displayed and ready for formatting.

Actually I decided to do this. So the `Show` component recieves the entire data set, then it splits it into the nessecarry parts.

This took approx 1 hour

##### <ins>Data Formatting</ins> - 30/07/19 1230 - https://trello.com/c/Gg88u6Ri

At this stage I'm simply sending all the data to each compoent - now I'm going to split it up into what is only nessecary - In this case security of data isn't important but a good guide is to only send what is needed rather than everything

Within the `Show` component I've decided to recieve the entire json data packet - this is to mimic an api type call with all data beign provided there.

Scope the data that is necessary rather than everything.

Data required for summary - json key names: 
- url
- name
- genres
- rating.average
- image
- summary

Data required for Episodes, I'll pre-porcess the data as the number of seasons aren't avaiable at a higher level and need to determine them (this will be used for the season filter) - what I'll do is store each episode in a object assigned to a season.

* name
* image
* summary
* season
* number

This took approx 1 hour

##### <ins>Responsive Card Deck</ins> - 31/07/2019 - 1700 - https://trello.com/c/GT5r8HlB

At this point I decieded to implement a responsive card deck, so as the browser changes witdth it will adjust the number of cards being displayed on each row - not only is this useful for differnt devices but also depending on the amount of episodes (via season) show will be responsive and look good.

I've finished the basic layout of this feature - the css is still a bit screwy - rather than focus on that I'm going to implement the sorting by season feature first - get that working and the fix up any formatting/css issues.

This took about 45 minutes

##### <ins>Season Episode Sorting</ins> - 1/08/2019  - 1300 - https://trello.com/c/tAKOG9j2

Create a method for sorting the episodes and also create a isActive directive to set the button as active and tie the soring method to that. Will also need to copy the episodes props to a new data var for manipulation

This took about an hour

##### <ins>Code Cleanup</ins> - 1/08/2019 - 1500 - https://trello.com/c/GPee0dDU

Fixed all the problem css and formatting - also redid the card deck to utilise the BootstrapVue lib rather than straight bootstrap 4.

Also added some shadows and hover animations

I forgot to add the date filter with the asc/desc ordering as well

This took about 2 hours including fishing off the documentation

### Conclusion/Thoughts/Improvements

```
1. What features would you like to build? 
2. What third-party services would you like to use? 
3. What technologies would you like to use? 
```

I'm relatively happy with the results - I would like to refactor the code to be a little more modular i.e. seperate out the several components in `Episodes`. Create some unit tests and hook it into an API (or at least dummy one up)

One thing I definetly don't want to use again is bootstrap - although I'm farmiliar with it, I believe its outdated and not the best choice for more mordern applications. With what to use; honestly I'm not sure, but I've heard good things about Foundation and Bulma

Some features that I would like to add

* Nicer loading transitions when altering the filters
* Add another menu for selecting the actual show - that way this could be used for any tv show
* Add expanding cards - so when you click on a card a dialog would open giving you more info
* Add some more filters - add a text search

In total I used 18 points - which equates to 9 hours of work - definetly thought I do it easily under the 8, but I did spend a good 2 hours doing this journal and preparing the trello board. 















