<template>
  <div class="container">
    <div class="posts">
        <div class="header-logo">
          <img src="../assets/img/logo.png" alt="SHAREロゴ">
        </div>
        <div class="home-logo">
          <img src="../assets/img/home.png" alt="ホームロゴ">
          <NuxtLink to="/home">ホーム</NuxtLink>
          </div>
        <div class="home-logo">
          <img src="../assets/img/logout.png" alt="ログアウト">
          <NuxtLink to="/login">ログアウト</NuxtLink>
        </div>
        <p>シェア</p>
        <form>
          <textarea name="message"  cols="35" rows="10"></textarea>
          <button class="btn">シェアする</button>
        </form>
      </div>

      <div class="posts-list">
        <ul>
          <li><h2>コメント</h2></li>
          <li><p>name</p><p><img class="icon" src="../assets/img/heart.png" alt="ハートのアイコン">0</p><p><img class="icon" src="../assets/img/cross.png" alt="削除アイコン"></p><br><p>新規投稿</p></li>
        </ul>
        <ul>
          <li><h2>コメント</h2></li>
          <li>
            <p>name</p>
          <br>
          <p>comment</p>
          </li>
        </ul>
        <form>
          <input type="text" name="comment">
          <button class="btn">コメント</button>
        </form>
      </div>
  </div>
</template>

<style scoped>
body {
  background-color: #000;
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
textarea {
  border-radius: 5px;
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
input {
  text-align: center;
  margin: 0 auto;
  margin-bottom: 10px;
  display: block;
  width: 530px;
  border-radius: 5px;
}
</style>
