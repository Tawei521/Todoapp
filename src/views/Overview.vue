<template>
  <div class="overview">
    <!-- Overview -->
    <!-- <h1>posts</h1> -->
    <!-- <div v-for="post in posts" :key="post.id">
            <h2>{{post.email}}</h2>
            <p>{{post.id}}</p>
        </div> -->

    <table class="table table-striped">
      <thead class="table-dark">
        <tr>
          <th scope="col">id</th>
          <th scope="col">name</th>
          <th scope="col">email</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="post in posts" :key="post.id">
          <!-- <th scope="row"></th> -->
          <td v-text="post.id"></td>
          <td v-text="post.name"></td>
          <td v-text="post.email"></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "overview",
  data() {
    return {
      posts: [],
    };
  },
  methods: {},
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/posts/1/comments")
      
      .then((response) => {
        this.posts = response.data;
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<style scoped>
.overview {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
  font-size: 40px;
  /* color: rgb(167, 167, 167); */
  color: rgb(182, 11, 182);
  font-weight: 600;
}
.table {
  font-size: 20px;
  color: rgb(182, 11, 182);
}
</style>
