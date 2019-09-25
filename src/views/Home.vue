<template>
  <div>
    <ion-card v-for="post in posts" :key="post.id" style="border: 1px solid blue;">
      <ion-card-content>
        <template v-if="post.data.thumbnail.startsWith('https://')">
          <img :src="post.data.thumbnail">
        </template>
        <ion-label color="light">
          {{post.data.title}}
        </ion-label>
        <ion-button color="tertiary" expand="full" @click="viewMore(post.data)">
          View More
        </ion-button>
      </ion-card-content>
    </ion-card>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      posts: []
    };
  },
  async mounted() {
    const response = await axios.get(
      "https://www.reddit.com/r/nextfuckinglevel.json"
    );
    this.posts = response.data.data.children;
  },
  methods: {
    viewMore(post) {
      // console.log(post);
      this.$router.push({ name: "detail", params: { post } });
    }
  }
};
</script>
