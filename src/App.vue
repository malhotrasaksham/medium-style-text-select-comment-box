<template>
  <div id="app">
    <h3>Heading One</h3>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi atque nostrum, est a in facere. Quis molestias consequuntur dignissimos fugit, eos amet illum deleniti quos, eaque laudantium unde, velit iusto.</p>
    <h3>Heading Two</h3>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi atque nostrum, est a in facere. Quis molestias consequuntur dignissimos fugit, eos amet illum deleniti quos, eaque laudantium unde, velit iusto.</p>
    <h3>Heading Three</h3>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi atque nostrum, est a in facere. Quis molestias consequuntur dignissimos fugit, eos amet illum deleniti quos, eaque laudantium unde, velit iusto.</p>
    <h3>Heading Four</h3>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi atque nostrum, est a in facere. Quis molestias consequuntur dignissimos fugit, eos amet illum deleniti quos, eaque laudantium unde, velit iusto.</p>
    <medium-style-comments></medium-style-comments>
  </div>
</template>

<script>
import MediumStyleComments from "@/components/medium-style-comments.vue";
export default {
  name: "App",
  components: {
    MediumStyleComments
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  position: relative;
}
</style>
