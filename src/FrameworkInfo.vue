<template>
  <div class="framework-info container">
    <b-card
    :title="name"
    :img-src="img"
    img-bottom
    tag="article"
    style="width: 20rem; height: 28rem;"
    class="mb-2">
    <b-card-text>
      Stars: {{stars}}
      <br>
      Forks: {{forks}}
      <br>
      Issues: {{issues}}
    </b-card-text>
  </b-card>
  </div>
</template>

<script>
export default {
  name: 'FrameworkInfo',
  props: ['name', 'img', 'stars', 'forks', 'issues']
}
</script>
