<template>
  <div class="dropdown">
    <button
      type="button"
      class="btn btn-sm dropdown-toggle"
      data-bs-toggle="dropdown"
      aria-expanded="false"
      @click="hello"
    >
      {{ label }}
    </button>
    <ul v-if="usersData?.length" class="dropdown-menu">
      <li v-for="user in usersData" :key="user.userId">
        <a class="dropdown-item" @click="handleClick(user)"
          >{{ user.first_name }} {{ user.last_name }}</a
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "UsersDropdown",
  props: {
    label: String,
    usersData: Object,
    user: Object,
  },

  methods: {
    hello() {
      console.log(this.usersData);
    },
    handleClick(user) {
      console.log(user, "jj");
      this.$emit("getPostsByUser", user);
    },
  },
};
</script>
