<template>
  <div>
    <p class="text-muted mb-0">Nama</p>
    <h6>{{ user.name }}</h6>

    <p class="text-muted mb-0">Username</p>
    <h6>{{ user.username }}</h6>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  props: {
    id: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {
      user: {},
    };
  },
  methods: {
    getUser() {
      axios.get(`/users/${this.id}`).then((response) => {
        this.user = response.data;
      });
    },
  },
  mounted() {
    this.getUser();
  },
};
</script>

<style></style>
