<template>
  <div class="row">
    <div class="pl-4 col-12"><strong>Target: </strong>{{ target.name }}</div>
    <div class="pl-4 col-12"><strong>Root Domain: </strong>{{ rootDomain.name }}</div>
    <div class="pl-4 col-12"><strong>Subdomains: </strong>{{ subdomainsCount }}</div>
    <div class="pl-4 col-12"><strong>Agents: </strong>{{ agentsCount }}</div>
  </div>
</template>

<script>

  import { mapState } from 'vuex'

  export default {
    name: 'TargetGeneralTag', 
    computed: mapState({
      target: state => state.targets.currentTarget,
      rootDomain: state => state.targets.currentRootDomain,
      subdomainsCount: state => state.targets.currentRootDomain.subdomains.length,
      agentsCount: state => state.agents.agents.length
    }), 
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>