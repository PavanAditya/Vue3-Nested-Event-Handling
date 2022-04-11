<template>
  <div class="main">
    <Navigation
      @getPostsByUser="getPostsByUser"
      :label="'All users'"
      :usersData="users"
    />
  </div>
</template>

<script>
import Navigation from "./components/Navigation";

export default {
  name: "Main",
  components: {
    Navigation,
  },
  props: {
    title: String,
    tagline: String,
  },

  data() {
    return {
      userId: "",
      users: [
        { userId: 1, first_name: "fn1", last_name: "ln" },
        { userId: 3, first_name: "fn3", last_name: "ln" },
        { userId: 2, first_name: "fn2", last_name: "ln" },
      ],
      posts: [],
      // more code
    };
  },

  methods: {
    getPostsByUser(user) {
      // get user id
      console.log(user, "kks");
      this.userId = user.userId;
    },
  },
};
</script>
