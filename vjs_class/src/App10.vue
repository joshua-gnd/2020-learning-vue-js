<template>
  <div id="app">
    <input v-model="newcomment" />
    <input v-model="newcommentID" @keyup.enter="postComments" />
    <button @click="postComments">add comment</button>

    <template>
      <el-table :data="comments" style="width: 100%">
        <el-table-column prop="id" label="ID" width="180"></el-table-column>
        <el-table-column prop="body" label="Comment" width="180"></el-table-column>
        <el-table-column prop="postId" label="POSTID"></el-table-column>
      </el-table>
    </template>
  </div>
</template>


<script>
import axios from "axios";
export default {
  name: "app",
  components: {},
  data() {
    return {
      comments: [],
      selected: "",
      newcomment: "",
      newcommentID: ""
    };
  },

  mounted() {
    this.getComments();
  },

  methods: {
    async postComments() {
      let response = await axios.post(
        "https://my-json-server.typicode.com/typicode/demo/comments",
        { body: this.newcomment, postId: this.newcommentID }
      );
      console.log(response);
      this.comments.push(response.data);
      this.newcomment = "";
      this.newcommentID = "";
    },

    async getComments() {
      let response = await axios.get(
        "https://my-json-server.typicode.com/typicode/demo/comments"
      );
      console.log(response);
      this.comments = response.data;
    },

    async updateComments() {
      let response = await axios.patch(
        "https://my-json-server.typicode.com/typicode/demo/comments/1",
        { body: "update" }
      );
      console.log(response);
    },

    async deleteComments() {
      let response = await axios.delete(
        "https://my-json-server.typicode.com/typicode/demo/comments/1"
      );
      console.log(response);
    },

    async multiplerequests() {
      let response = await axios.all([
        axios.put(
          "https://my-json-server.typicode.com/typicode/demo/comments/1",
          { body: "update" }
        ),
        axios.delete(
          "https://my-json-server.typicode.com/typicode/demo/posts/1"
        )
      ]);

      console.log(response[0]);
    }
  }
};
</script >

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  list-style-type: none;
}
.online {
  background-color: green;
}

.default {
  background-color: blue;
}

.offline {
  background-color: gray;
}

.statusbox {
  color: white;
  width: 40px;
  height: 50px;
}
</style>