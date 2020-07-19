<template>
  <div id="app">
    <el-form :inline="true">
      <el-form-item label="First Name">
        <el-input v-model="first_name" placeholder="first name"></el-input>
      </el-form-item>
      <el-form-item label="Last Name">
        <el-input v-model="last_name" placeholder="first name"></el-input>
      </el-form-item>

      <el-form-item>
        <el-button type="primary" @click="createStudents">add</el-button>
      </el-form-item>
    </el-form>

    <template>
      <el-table :data="students" style="width: 100%">
        <el-table-column prop="first_name" label="First Name" width="180"></el-table-column>
        <el-table-column prop="last_name" label="Last Name" width="180"></el-table-column>
        <el-table-column label="Courses">
          <template slot-scope="scope">{{getCourseVerbose(scope)}}</template>
        </el-table-column>
      </el-table>
    </template>
    <div class="space"></div>

    <el-form :inline="true">
      <el-form-item label="Name">
        <el-input v-model="name" placeholder="name"></el-input>
      </el-form-item>
      <el-form-item label="Level">
        <el-input v-model="level" placeholder="level"></el-input>
      </el-form-item>

      <el-form-item>
        <el-button type="primary" @click="createCourse">add</el-button>
      </el-form-item>
    </el-form>Courses
    <template>
      <el-table :data="courses" style="width: 100%">
        <el-table-column prop="name" label="Name" width="180"></el-table-column>
        <el-table-column prop="level" label="Level" width="180"></el-table-column>
        <el-table-column label="Students">
          <template slot-scope="scope">{{getStudentVerbose(scope)}}</template>
        </el-table-column>
      </el-table>
    </template>

    <li v-for="course in students.course" :key="course._id">{{course.name}}</li>
  </div>
</template>


<script>
import axios from "axios";

export default {
  name: "app",
  components: {},
  data() {
    return {
      todos: [],
      selected: "",
      newcomment: "",
      newcommentID: "",
      slotname: "slot2",
      userinput: "hello",
      componentname: "searchText",
      countries: [],
      students: [],
      courses: [],

      first_name: "",
      last_name: "",
      name: "",
      level: "",
      description: ""
    };
  },

  mounted() {
    this.getStudents();
    this.getCourses();
  },

  methods: {
    async postComments() {
      let response = await axios.post(
        "https://my-json-server.typicode.com/typicode/demo/comments",
        { body: "hello world", postId: "3" }
      );
      console.log(response);
      this.comments.push(response.data);
      this.newcomment = "";
      this.newcommentID = "";
    },

    async getComments() {
      let response = await axios.get("https://localhost:4000/api/todos");
      console.log(response);
      this.todos = response.data;
    },

    async updateComments() {
      let response = await axios.put(
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
    },

    async getStudents() {
      let response = await axios.get("http://localhost:4000/api/students");
      console.log(response);
      this.students = response.data;
    },

    async createStudents() {
      let response = await axios.post("http://localhost:4000/api/students", {
        first_name: this.first_name,
        last_name: this.last_name
      });
      console.log(response);
      //this.student=response.data
    },

    async createCourse() {
      let response = await axios.post("http://localhost:4000/api/courses", {
        name: this.name,
        level: this.level
      });
      console.log(response);
    },

    async getCourses() {
      let response = await axios.get("http://localhost:4000/api/courses");
      console.log(response);
      this.courses = response.data;
    },

    getCourseVerbose(scope) {
      return scope.row.course
        .map(item => {
          return item.name;
        })
        .join(", ");
    },

    getStudentVerbose(scope) {
      return scope.row.students
        .map(item => {
          return item.first_name + " " + item.last_name;
        })
        .join(", ");
    }
  }
};
</script>

<style>
#demo-form-inline {
  background-color: green;
}

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

.space {
  height: 100px;
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

