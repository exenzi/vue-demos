<template>
  <ul>
    <li v-for="link in links">
      <a :href="link.url" target="_blank"><font-awesome-icon :icon="link.classes" /> {{ link.text }}</a>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          url: 'https://github.com/exenzi',
          text: 'Max Rokitsky',
          classes: ['fab', 'github-alt']
        },
        {
          url: 'https://github.com/lukePeavey/quotable',
          text: 'Quotable API',
          classes: ['fab', 'github-alt']
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
ul {
  position: fixed;
  right: 10px;
  top: 10px;
  list-style: none;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  background-color: white;
  padding: 10px;
  border-radius: 10px;
  gap: 5px;
}

a {
  text-decoration: none;
  color: black;
  font-family: sans-serif;
  font-size: .9rem;
}
</style>