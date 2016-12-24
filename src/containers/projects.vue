<template lang="html">
  <div id="projects">
    <div class="columns">
      <div class="column is-half">
        <div class="notification">
          List of fake projects, courtesy of mocky.io ...
        </div>
        <div class="">
          <table class="table">
            <thead>
              <tr>
                <th>Project Name</th>
                <th>Assigned To</th>
                <th>Priority</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="item in projects">
                <td>{{item.name}}</td>
                <td>{{item.assignedTo}}</td>
                <td>{{item.priority}}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'projects',
  data: function () {
    return {
      projects: []
    }
  },
  methods: {
    loadProjects: function () {
      this.$http.get('http://www.mocky.io/v2/585e03ce100000b82c501e8e').then((response) => {
        // depending on your api, you may or may not have to make the .json() call
        // if your repsonse.body is null, try this
        response.json()
        this.projects = response.body
      }, (err) => {
        console.log(err)
      })
    }
  },
  mounted: function () {
    this.loadProjects()
  }
}
</script>

<style lang="css">
</style>
