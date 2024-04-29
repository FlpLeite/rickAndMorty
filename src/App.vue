<script setup>
import {ref} from "vue"

let num = ref(0)
</script>

<template>
  <nav class="navbar">
    <div class="container-fluid">
      <router-link class="navbar-brand" to="/">
        <img src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Rick_and_Morty.svg" height="80vh" alt="">
      </router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbar" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" aria-current="page" to="/"> <b>Home</b> </router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" aria-current="page" to="/about"><b>About</b></router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <div class="main">
      <router-view></router-view>
  </div>
  
  <footer>
    <div class="footer-inf">
      FlpLeite | Desenvolvedor front-end | {{ new Date().getFullYear() }}
    </div>
  </footer>
</template>

<style>

  body{
    background-color:  #87d1db;
  }

  .container-fluid {
    display: flex;
    align-items: flex-start;
  }

  .navbar{
    background-color: #4cb5c3;
    position: sticky;
    top: 0;
    left: 0;
    z-index: 1; 
  }

  .nav-item{
    font-size: large;
  }

  footer{
    background-color: #4cb5c3;
    box-shadow: 0px -15px 75px #4cb5c3;
    position: sticky;
    bottom: 0;
    width: 100%;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    height: 50px;
    
  }

  .footer-inf{
    margin-top: 15px;
  }

  .card{
    margin-bottom: 15px;
    border-radius: 10px;
  }

  .nav-link{
    float: right;
    margin-right: 10px;
  }

  .navbar-toggler{
    display: flex;
    margin-top: 30px;
    margin-right: 5px;
  }

</style>