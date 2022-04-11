<template>
  <div class="navigation">
    <UsersDropdown
      @getPostsByUser="getPostsByUser"
      :label="'All users'"
      :usersData="usersData"
    />
  </div>
</template>

<script>
import UsersDropdown from "./UsersDropdown";

export default {
  components: {
    UsersDropdown,
  },
  props: {
    usersData: Object,
  },
  data() {
    return {
      users: [],
    };
  },
  methods: {
    getPostsByUser(user) {
      // get user id
      console.log(user, "js");
      this.$emit("getPostsByUser", user);
    },
  },
  emits: ["getPostsByUser"],
};
</script>
