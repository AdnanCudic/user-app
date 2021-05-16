<template>
  <div class="userMain" >
    <div class="userList"
      v-for="user in userInfo.data"
      :key="user.id"
      :firstname="user.first_name"
      :lastname="user.last_name"
      :email="user.email"
      :avatar="user.avatar"
      
    >      <div class="userPhoto"> <img :src="user.avatar" /> </div>    
      <div class="userBlock">

          <li><strong>{{ user.first_name }} {{ user.last_name }}</strong></li>
          <li>
            <a :href="'mailto:' + user.email">{{ user.email }}</a>
          </li>
      </div>
    </div>

    <button @click="(selectedPage = 1), getUserInfo()">Page 1</button>
    <button @click="(selectedPage = 2), getUserInfo()">Page 2</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      selectedPage: "",
      userInfo: [{}],
    };
  },

  methods: {
    getUserInfo() {
      axios
        .get("https://reqres.in/api/users" + "?page=" + this.selectedPage)
        .then((response) => {
          this.userInfo = response.data;
        })
    },
  },
  created() {
    this.getUserInfo();
  },
};
</script>

<style>
.userMain {
border:3px outset whitesmoke;
width: 30rem;
margin: auto;
background-color: whitesmoke;
}
.userList {

  margin: auto;
  width: 400px;
  display: flex;
  border-bottom: 1px  dashed grey;
}
.userList li {
  list-style: none;
  }
.userList li a {
  text-decoration: none;
  color: gray;
}
.userList li a:hover {
  color: lightseagreen;
}
.userList img {
border-radius: 100%;
width: 5rem;
height: 5rem;
}
.userBlock {
width:250px;
margin: auto;
text-align: left;

}
.userPhoto {
  width: 50px;
  padding: 0.4rem;

}

button{
  border:none;
  background-color: transparent;
  color: grey;
  padding: 1rem;
}
button:hover{
  color: green;
}
</style>
