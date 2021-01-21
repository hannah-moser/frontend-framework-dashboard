<template>
  <div id="app">
    <h1>Check Out These Sick Framework Options</h1>
    <b-button-group class="p-2">
      <b-button v-on:click="getStars">Stars</b-button>
      <b-button v-on:click="getForks">Forks</b-button>
      <b-button v-on:click="getIssues">Issues</b-button>
    </b-button-group>

    <b-card-group deck class="justify-content-md-center">
      <div v-for="framework in frameworks" v-bind:key="framework.id">
        <FrameworkInfo :name="framework.name" :img="framework.img" :stars="framework.stars" :forks="framework.forks" :issues="framework.issues"></FrameworkInfo>
      </div>
    </b-card-group>
  </div>
</template>

<script>
import FrameworkInfo from './components/FrameworkInfo.vue'

export default {
  name: 'App',
  components: {
    FrameworkInfo
  },
  data: function() {
    return {
      frameworks: [
        {id: 1, name: 'React', img: require('@/assets/react_logo.png'), stars: null, forks: null, issues: null},
        {id: 2, name: 'Angular', img: require('@/assets/angular_logo.png'), stars: null, forks: null, issues: null},
        {id: 3, name: 'Ember', img: require('@/assets/ember_logo.png'), stars: null, forks: null, issues: null},
        {id: 4, name: 'Vue', img: require('@/assets/vue_logo.png'), stars: null, forks: null, issues: null}
      ],
      githubs: [
        {id: 1, owner: '/facebook', repo: '/react'},
        {id: 2, owner: '/angular', repo: '/angular'},
        {id: 3, owner: '/emberjs', repo: '/ember.js'},
        {id: 4, owner: '/vuejs', repo: '/vue'}
      ]
    }
  },
  methods: {
    getStars: function () {
      this.githubs.forEach(github => {
        this.getRepoData(github.owner, github.repo)
          .then((response) => {
            this.frameworks[github.id-1].stars = response.data.stargazers_count
          })
      })
    },
    getForks: function () {
      this.githubs.forEach(github => {
        this.getRepoData(github.owner, github.repo)
          .then((response) => {
            this.frameworks[github.id-1].forks = response.data.forks_count
          })
      })
    },
    getIssues: function () {
      this.githubs.forEach(github => {
        this.getRepoData(github.owner, github.repo)
          .then((response) => {
            this.frameworks[github.id-1].issues = response.data.open_issues_count
          })
      })
    },
    getRepoData: function(owner, repo) {
      return this.$http.get("https://api.github.com/repos" + owner + repo)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
