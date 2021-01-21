# Framework Dashboard

This dashboard can be used to view different attributes of various frontend frameworks. The frameworks analyzed here are:
* React
* Angular
* Ember
* Vue

For each framework, the following information can be compared:
* **Stars** - These are commonly used to indicate that a developer likes a repository, or wants to keep an eye on it moving forward, saved on their personal github account as favorite.
* **Forks** - This indicates how many people copied the repository, allowing them to experiment freely with it without affecting the original code.
* **Commits** - This can be used to gauge how active development is within the repository, indicating that developers have made updates, added features, resolved issues, or generally maintained the code. 

The dashboard is a Vue app utilizing [BootstrapVue](https://bootstrap-vue.org/) styling and all stats are retrieved from the [GitHub API](https://docs.github.com/v3/) using an [axios](https://github.com/axios/axios) integration for HTTP requests. All requests are made without a page refresh, utilizing Vue's reactive two way binding tendencies to pull updated data into the DOM in real time. 

## Check It Out!
This [Frontend Framework Dashboard](https://frontend-framework-dashboard.onrender.com/) is hosted on render.

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```
