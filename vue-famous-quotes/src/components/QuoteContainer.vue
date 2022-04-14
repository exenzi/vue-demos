<template>
  <div class="quote-container">
    <Loader v-if="!content" class="loader"/>
    <Quote :quote="content" />
    <footer v-if="content" class="footer">
      <span>{{ author }}</span>
      <button @click="updateQuote">Update</button>
    </footer>
  </div>
</template>

<script>
import Quote from "./Quote.vue";

import axios from "axios";
import Loader from "./Loader.vue";

export default {
  components: {
    Quote,
    Loader
},
  data() {
    return {
      content: null,
      author: null,
    }
  },
  mounted() {
    this.updateQuote();
  },
  methods: {
    updateQuote() {
      this.content = null;
      this.author = null;

      const options = {
        method: 'GET',
        url: 'https://api.quotable.io/random',
      };

      axios.request(options).then(response => {
        const data = response.data;
        setTimeout(() => {
          this.content = data.content;
          this.author = data.author;
        }, 1000)
      }).catch(error => {
        console.error(error);
      });
    }
  }
}
</script>

<style lang="scss" scoped>
.loader {
  align-self: center;
}

.quote-container {
  background-color: white;
  width: 50%;
  max-width: 800px;
  border-radius: 20px;
  padding: 30px;
  display: flex;
  flex-direction: column;

  @media (max-width: 1100px) {
    width: 70%;
  }

  @media (max-width: 700px) {
    width: 90%;
  }
}

.footer {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

button {
  align-self: flex-end;
  font-size: 1rem;
  padding: 10px 16px;
  background-color: hsl(201, 100%, 80%);
  border: none;
  color: white;
  border-radius: 5px;
  font-family: 'EB Garamond', serif;

  &:hover {
    background-color: hsl(201, 100%, 70%);
    cursor: pointer;
    outline: hsl(201, 100%, 90%) solid 2px;
  }

  &:active {
    background-color: hsl(201, 100%, 60%);
  }
}

span {
  font-style: italic;
}
</style>