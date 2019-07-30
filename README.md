# Setup

To set up the application please do the following - command examples for macOS

* Install VueCLI
  * Install Yarn - `brew install yarn` (for [`brew`](https://brew.sh/)`installation )
  * Install VueCLI - `yarn global add @vue/cli`
  * Check its installed correctly - `vue —version`
* To run:
  * `yarn serve`

```
# mf-test-project

## Project setup
​```
yarn install
​```

### Compiles and hot-reloads for development
​```
yarn run serve
​```

### Compiles and minifies for production
​```
yarn run build
​```

### Run your tests
​```
yarn run test
​```

### Lints and fixes files
​```
yarn run lint
​```

### Run your unit tests
​```
yarn run test:unit
​```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
```

# Mentally Friendly Notes/Journal

### <ins>Descisions and Planning - 30/07/2019 0830</ins>

On top of the documentation and trello board I've decieded to write a journal for a verbose experience of my thoughts and process's throughout this projects life cycle. 

I recieved the design brief yesterday and have had the luxury of 24 hours to think about how I'm going to approach this project. 

##### Technologies

* Git/Github/Git-Flow - Will utilise the git-flow working off the `develop`branch, once the project is done do a `release`. Use github to display the code and place this as the README.md
* Vue.js/Vue-CLI - Utilise Vue.js as the frontend framework following its design guide and principles, also use Vue-CLI for tooling and project layout
* Trello/Markdown - Use trello as a high level task/feature list, utilise time-estimation within cards. For all other notes and docuumentaton use markdown.
* BootstrapVue - utilise bootstrap-vue for css https://bootstrap-vue.js.org/

##### Descions

* Minimise the use of external liabries - make the code as vinalla Vue.js as possible
* Make the site responsive to widths
* Incorperate some basic testing of the project
* Make it [Zen](https://nicoledominguez.com/assets/public/zen-py.png) - although this isn't a python project I belive these are great points to guide me along the path

My main goal is to complete the two sorting stories provieded in the design brief. To get there I'm going to create some basic stories outlining what I need to do to get to that point. 

I've set up trello with 3 lists; `Todo`: tasks that are in the backlog, `Doing`: currently in progress and `Done`: things that have been completed also will place an actual time spent at this point to identify and discrepencies in my estimates.

> 1 point = 30 minutes

![image-20190730090236633](/Users/tcrha/Library/Application Support/typora-user-images/image-20190730090236633.png)

Intial board, I expect this to change as I go down the rabbit hole, but this has the overall tasks, but generally I'll then break down these tasks into smaller stories/features. I'll also link the git commits into each card and where they fit into the dev cycle.

####<ins>Skeleton</ins>

Intially I set up all the nesseary plugins and tools outlined above. 

* Created a main component to encapuslate a show - this way if the json is extended to more shows we can reuse this component rather than creating a new one for each show
  * With in this component currently there are two other components Summary and Episode - I'll probably create another for the Episode card
  * `Summary.vue`simply contains the summary of the series
  * `Episodes.vue` contains all the sorting and display code for the episodes guide.
* Currently I've loaded the json file as part of the entire App scope - I may change this to sort the data and then prop up each component with there nessecary data - bit for now I just want to get the data displayed and ready for formatting.

Actually I decided to do this. So the `Show` component recieves the entire data set, then it splits it into the nessecarry parts.

