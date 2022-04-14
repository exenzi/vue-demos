<template>
<div class="container">
  <QuoteContainer></QuoteContainer>
  <GithubLink />
</div>
</template>

<script>
import QuoteContainer from "./components/QuoteContainer.vue";
import GithubLink from "./components/GithubLink.vue";

export default {
  components: {
    QuoteContainer,
    GithubLink,
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=EB+Garamond&display=swap');

*, *::before, ::after {
  box-sizing: border-box;
}

body {
  padding: 0;
  margin: 0;
  font-family: 'EB Garamond', serif;
}

#app {
  width: 100%;
  height: 100%;
}

.container {
  min-height: 100vh;
  width: 100%;
  background-color: hsl(201, 100%, 80%);
  overflow: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
