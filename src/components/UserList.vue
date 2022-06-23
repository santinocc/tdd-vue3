<template>
  <div class="card">
    <div class="card-header text-center">
      <h3>Users</h3>
    </div>
    <ul class="list-group list-group-flush">
      <li
        class="list-group-item list-group-item-action"
        v-for="user in page.content"
      >
        {{ user.username }}
      </li>
    </ul>
    <button @click="loadPrevious()" v-if="page.page !== 0">
      &lt; previous
    </button>
    <button @click="loadNext()" v-if="page.totalPages > page.page + 1">
      next &gt;
    </button>
  </div>
</template>

<script>
import { loadUsers } from "../api/apiCalls";
export default {
  data() {
    return {
      page: {
        content: [],
        page: 0,
        size: 0,
        totalPages: 0,
      },
    };
  },

  async mounted() {
    const response = await loadUsers();
    this.page = response.data;
  },
  methods: {
    async loadNext() {
      const response = await loadUsers(this.page.page + 1);
      this.page = response.data;
    },
    async loadPrevious() {
      const response = await loadUsers(this.page.page - 1);
      this.page = response.data;
    }
  },
};
</script>
