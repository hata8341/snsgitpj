<template>
  <div class="container">
      <div class="posts">
        <div class="header-logo">
          <img src="../assets/img/logo.png" alt="SHAREロゴ">
        </div>
        <div class="home-logo">
          <img src="../assets/img/home.png" alt="ホームロゴ">
          <p>ホーム</p>
          </div>
        <div class="home-logo">
          <img src="../assets/img/logout.png" alt="ログアウト">
          <NuxtLink to="/login" @click="logout">ログアウト</NuxtLink>
        </div>
        <p>シェア</p>
        <form>
          <textarea name="message"  cols="35" rows="10"></textarea>
          <button class="btn">シェアする</button>
        </form>
      </div>

      <div class="posts-list">
        <ul>
          <li><h2>ホーム</h2></li>
          <li><p>name</p><p><img class="icon" src="../assets/img/heart.png" alt="ハートのアイコン">{{count}}</p><p><img class="icon" src="../assets/img/cross.png" alt="削除アイコン"></p><NuxtLink to="/comment"><img class="icon" src="../assets/img/detail.png" alt="コメントのアイコン"></NuxtLink><br><p>新規投稿</p></li>
        </ul>
      <p>{{post}}</p>
      </div>
  </div>
</template>

<script>
import firebase from '~/plugins/firebase'
export default {
  data() {
    return {
      message: null,
      count: 0,
      post: 'ログインできていません'
    }
  },
  methods: {
    logout() {
      firebase
      .auth()
      .signOut()
      .then(() => {
        alert('ログアウトが完了しました')
        this.$router.replace('/login')
      })
    },
  },
  created() {
    firebase.auth().onAuthStateChanged((user) => {
      if (user) {
        this.post = 'ログインしました。'
      }
    })
  },
}
</script>

<style scoped>
body {
  background: #000;
}
.container {
  display: flex;
  background: #000;
}
.posts {
  width: 290px;
}
.header-logo img{
  width: 130px;
}
.home-logo img {
  width: 50px;
}
p {
  display: inline-block;
  color: #fff;
}
.btn {
  width: 100px;
  padding: 5px;
  text-align: center;
  text-decoration: none;
  color: #fff;
  background: blueviolet;
  border-bottom: 2px solid #005601;
  border-radius: 30px;
  transition: .0s;
  display: block;
  margin-top: 5px;
  margin-left: auto;
}
.btn:hover {
  cursor: pointer;
}
.btn:active {
  background: #005601;
  transform: translate3d(0, 2px,0);
  transition: .0s;
  border-bottom: none;
}
a {
  color: #eee;
  text-decoration: none;
}
.posts-list {
  width: 900px;
  /* border: 1px solid #eee; */
  margin-left: 15px;
}
ul {
  padding-left: 0px;
}
li {
  color: #eee;
  border: 1px solid #eee;
  border-top: none;
  border-right: none;
  list-style: none;
}
.icon {
  width: 50px;
}
</style>
