<template>
  <div>
    <header class="shadow-sm header-principal">
    <nav class="navbar navbar-expand-lg">
      <div class="container-fluid">
        <h1 class="naranja">{{ $route.name }} </h1>
        <button type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation" id="hamburguesa">
          <i class="bi bi-list fs-3 naranja"></i>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="nav-bar mb-5 menu">
          <li>
            <i class="bi bi-shield-check fs-3 naranja"></i>
            <router-link class="text-black" to="/privacidad">Politicas de privacidad</router-link>
          </li>
          <li>
            <i class="bi bi-escape fs-3 text-danger"></i>
            <button id="cerrar__sesion" @click="logout">Cerrar sesión</button>
          </li>
        </ul>
        </div>
      </div>
    </nav>
  </header>
  </div>
</template>

<script>
  import {logout} from '../services/autenticacion.js';
  import {usePinia} from '../store/pinia.js';
  export default {
    setup(){
      
      const pinia = usePinia();
      return {pinia}
      
    },
    data(){
      return {
        menu: false
      }
    },
    methods: {  
      logout
    }
  }
</script>

<style scope>
  .header-principal{
    background:white;
    width: 100%;
    display: flex;
    justify-content: left;
    flex-direction: row;
    position: fixed;
    top: 0;
    left: 0;
    padding: 10px 0 10px;
    z-index: 1;
  }
  .header-principal h1{
    margin: 5px 25px 5px;
    font-size: 1.3em;
  }

  .header-principal nav{
    transition: all 0.4s ease-in-out;
    width: 100%;
    background: url('../assets/logo_biufort_azul.png');
    background-position: center center;
    background-size: contain;
    background-repeat: no-repeat;
  }
  .menu__burger{
    position:fixed;
    left: 5%;
  }
  .header-principal button{
    background-color: transparent;
    outline: none;
    border: none;
    color: #FF4D01;
    margin-left: 0%;
    padding: 0%;
    font-weight: bold;
  }
  #cerrar__sesion{
    color: rgba(187, 4, 4, 0.79);
  }

  .navbar > .container-fluid {
    justify-content: flex-start!important;
    width: 100%;
}

.menu {
  margin: 20px 0 0!important;
}

#navbarNav ul {
  padding-left: 0%!important;
  height: 700px;
  background: #ffffffe5;
}

.menu li {
  padding: 10px 0 10px 50px;
  width: 100vw;
  box-shadow: 0px 0px 5px -3px rgba(0,0,0,0.33);
  -webkit-box-shadow: 0px 0px 5px -3px rgb(0 0 0 / 33%);
  -moz-box-shadow: 0px 0px 5px -3px rgba(0,0,0,0.33);
}

.menu i {
  margin-right: 15px;
}

.container, .container-fluid, .container-xxl, .container-xl, .container-lg, .container-md, .container-sm {
    --bs-gutter-x: 0!important;
}

#hamburguesa {
    margin: 0 20px 5px auto;
}

.navbar {
  --bs-navbar-padding-y: 0!important;
}

</style>