<template lang="">
  <div class="card">
    <div class="card-header">
      {{text}}
    </div>
    <div class="card-body">
      <blockquote class="blockquote mb-0">
        <p>{{title}}</p>
        <footer class="blockquote-footer">
          Visit my portfolio <a :href="url">{{ text }}</a>
        </footer>
      </blockquote>
    </div>
  </div>
</template>
<script>
export default {
    props: ['url','title','text']
};
</script>
<style lang=""></style>
