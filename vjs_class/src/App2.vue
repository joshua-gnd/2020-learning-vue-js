
<template>
  <div id="app">
    {{message *2}}
    {{htmlcontent}}
    <br />
    {{capitals}}
    <br />
    {{length}}
    <h1 v-once>v-once (doesn't update): {{message}}</h1>

    <a v-bind:[attribute]="url">link1</a>

    <a v-bind:href="url">link2</a>

    <div class="statusbox" v-bind:class="{online:isOnline, offline:isOffline}">On/Off</div>

    <p v-if="visible">today is monday</p>

    <div v-html="htmlcontent">shit in here gets ignored</div>
    <!-- conditional rendering -->
    <p v-if="admin">change settings</p>
    <p v-else-if="user">you don't have permission to change settings</p>
    <p v-else>please login in</p>

    <template v-if="loginType==='username'">
      <label for>username</label>
      <input type="text" placeholder="enter username" />
    </template>

    <template v-else-if="loginType==='email'">
      <label for>Email</label>
      <input type="text" placeholder="Enter your email address" />
    </template>
  </div>
</template>

<script>
// Create two style classes - css style
// Use vbind to attach them to an element in your DOM based on boolean values stored in your data object - data in the app
// Create a computed property for those classes - vbind class logical function to dom

export default {
  name: "app",
  // components: {},
  data() {
    return {
      message: "fullstack",
      htmlcontent: '<h1 style="color:red">welcome!</h1>',
      url:
        "https://www.bb.undp.org/content/barbados/en/home/covid-19--response-programme/island-hack-prototype-challenge.html",
      attribute: "href",
      visible: false,
      isOnline: false,
      isOffline: true,
      user: true,
      loginType: "username",
      possibleClasses: {},
      admin: true,
      username: false
    };
  },

  computed: {
    capitals: function() {
      return this.message.toUpperCase();
    },

    length: function() {
      var stringlength = this.message.length;
      var stringval = this.message;

      return stringval + "  " + stringlength;
    },
    classObject: function() {
      return {
        online: this.isOnline && !this.isOffline,
        offline: this.isOffline && !this.isOnline
      };
    }
  }
};
</script>

<style>
.online {
  width: 16px;
  height: 16px;
  background-color: green;
}

.offline {
  background-color: red;
}
</style>