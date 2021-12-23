<template>
  <p v-if="$fetchState.pending">Fetching users...</p>
  <p v-else-if="$fetchState.error">We're sorry! An error occurred :(</p>
  <div v-else class="text-center my-5">
    <h1 class="font-light text-4xl py-5">What do users have to say about us</h1>
    <div class="mb-20">
      <div
        v-for="user of users"
        :key="user.login.uuid"
        class="
          bg-gray-100
          p-5
          w-2/4
          mx-auto
          my-5
          flex
          items-center
          justify-around
          rounded-md
        "
      >
        <div class="px-3">
          <img class="rounded-full" :src="user.picture.large" />
        </div>
        <div class="font-light px-3">
          {{ user.name.first }} {{ user.name.last }}
        </div>
        <div>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit
          reiciendis sed mollitia ex at? Eius voluptatum reprehenderit ipsa
          possimus et tempora suscipit eligendi atque accusamus?
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [],
    };
  },
  async fetch() {
    const response = await fetch("https://randomuser.me/api/?results=10");
    const data = await response.json();
    this.users = data.results;
  },
};
</script>

<style>
</style>