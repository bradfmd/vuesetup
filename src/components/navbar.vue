<template lang="html">
  <nav class="nav has-shadow" >
    <div class="nav-left">
      <router-link class="nav-item is-brand" to="/">
        Vue Project
      </router-link>
      <router-link class="nav-item is-tab" to="/dashboard">
        <i class="fa fa-dashboard"></i> Dashboard
      </router-link>
      <router-link class="nav-item is-tab" to="/projects">
        <i class="fa fa-list-alt"></i> Project List
      </router-link>
    </div>
    <div class="nav-right">
      <span class="nav-item">
        <a class="button">Logout</a>
      </span>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'navbar'
}
</script>

<style lang="css">

</style>
