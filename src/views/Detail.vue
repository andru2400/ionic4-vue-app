<template>
    <ion-card>
      <ion-card-header>
        <ion-label>
            {{props.post.title}}
        </ion-label>
        <ion-card-content>

        </ion-card-content>
      </ion-card-header>
    </ion-card>
</template>


<script>
export default {
  props: ["params"],
  data() {
    return {
      image: "",
      props: []
    };
  },
  mounted() {
    // console.log(this.props);
    this.props = this.$route.params;
    // console.log(this);
  }
};
</script>