<template>
  <div id="app">

    <div class="" style="margin:0;padding:0!important">
      <slider :item="images"></slider>
      <!-- <img v-else src="./assets/slide-1.png" style="width:100%" alt=""> -->
    </div>

    <div id="nav">
      <div class="img-logo">
        <img class="img" src="./assets/logo.png" alt="imagem aqui">
      </div>
      <div class="container">
        <div class="row">
          <div class="col right">
            <router-link class="menu-item" to="/inicio">Inicio</router-link>
            <router-link class="menu-item" to="/fotos">Fotos</router-link>
            <router-link class="menu-item" to="/servicos">Serviços</router-link>
            <router-link class="menu-item" to="/localizacao">Localização</router-link>
          </div>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="row">
        <div class="slide-img">
          <hooper class="down">
            <slide>
              <img src="./assets/slide-1.png" alt="imagem aqui">
            </slide>
            <slide>
              <img src="./assets/slide-2.png" alt="imagem aqui">
            </slide>
            <slide>
              <img src="./assets/slide-3.png" alt="imagem aqui">
            </slide>
          </hooper>
        </div>
      </div>
    </div>
    <div class="container pesquisa">
      <div class="row">
        <button class="col col-1 btn btn-primary menu-btn">Quartos</button>
        <button class="col col-1 btn btn-primary menu-btn">Veículos</button>
        <button class="col col-1 btn btn-primary menu-btn">Espaço</button>
        <button class="col col-1 btn btn-primary menu-btn">Combo</button>
      </div>
      <div class="row">
        <div class="col col-3">
          Que tipo de quarto?
        </div>
        <div class="col col-2">
          Check-in
        </div>
        <div class="col col-2">
          Check-out
        </div>
        <div class="col col-1">
          Adulto
        </div>
        <div class="col col-1">
          Crianças
        </div>
      </div>
      <div class="row">
        <select class="col col-3 selectpicker form-control" name="tipo" id="tipo">
          <option value="simples">Simples</option>
          <option value="duplo">Duplo</option>
          <option value="suite-simple">Suite Simples</option>
          <option value="suite-dupla">Suite Dupla</option>
        </select>
        <date-picker class="col col-2" v-model="checkin" valueType="format"></date-picker>
        <date-picker class="col col-2" v-model="checkout" valueType="format"></date-picker>
        <div class="col col-1">
          <input class="form-control" type="number">
        </div>
        <div class="col col-1">
          <input class="form-control" type="number">
        </div>
        <button class="col col-2 btn btn-primary">Buscar</button>
      </div>
    </div>
    <div class="container">
      <div class="row">
        <div class="col col-12 title">
          <h2>Como funciona a reserva?</h2>
          <h5>No LPIIHOTEL, o sistema de reserva é bem simples. São 3 passos que são seguidos.</h5>
        </div>
      </div>
      <div class="row">
        <div class="col col-4 container-sis">
          <font-awesome-icon class="icon-tam" icon="search"/>
          <h6>Onde você busca o serviço que mais lhe agrada.</h6>
        </div>
        <div class="col col-4 container-sis">
          <font-awesome-icon icon="calendar" />
          <h6>Selecionar o dia que desejar ter esse serviço.</h6>
        </div>
        <div class="col col-4 container-sis">
          <font-awesome-icon icon="id-card" />
          <h6>Após fazer todos os procedimentos anteriores, é hora de confirmar e efetuar o pagamento.</h6>
        </div>
      </div>
      <div class="row mais-vendidos">
        <div class="col col-3">
          <img class="img-hotel" src="./assets/hotel-1.png" alt="">
        </div>
        <div class="col col-3">
          <img class="img-hotel" src="./assets/hotel-2.png" alt="">
        </div>
        <div class="col col-3">
          <img class="img-hotel" src="./assets/hotel-3.png" alt="">
        </div>
        <div class="col col-3">
          <img class="img-hotel" src="./assets/hotel-4.png" alt="">
        </div>
      </div>
    </div>
    <!-- <router-view/> -->
  </div>
</template>

<script>
import { Hooper, Slide } from 'hooper'
import DatePicker from 'vue2-datepicker';
import 'vue2-datepicker/index.css';
import 'hooper/dist/hooper.css'

import slider from './components/Slider'

export default {
  name: 'menu',
  components: {
    Hooper,
    Slide,
    DatePicker,
    slider
  },
  data () {
    return {
      checkin: null,
      checkout: null,
      images: {
        id: '1',
        imagesUrl: [
          './assets/slide-1.png',
          './assets/slide-2.png',
          './assets/slide-3.png'
        ],
        slideError: false
      } 
    }
  },
  created () {
    this.images.imagesUrl.push('./assets/slide-1.png')
    this.images.imagesUrl.push('./assets/slide-2.png')
    this.images.imagesUrl.push('./assets/slide-3.png')
  }
}
</script>

<style lang="scss">
@import 'node_modules/bootstrap/scss/bootstrap';
@import 'node_modules/bootstrap-vue/src/index.scss';

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#nav {
  position: fixed;
  width: 100%;
  z-index: 9999;
  background-color: #fff;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #4477ff;
}

.img-hotel {
  width: 10rem;
  height: 5rem;
}

.mais-vendidos {
  margin-top: 3rem;
  margin-bottom: 3rem;
}

.down {
  z-index: 0000;
}

.pesquisa {
  // border-style: solid;
  margin-top: 18rem;
  z-index: 9999;
}

.reserva {
  background-color: #fff;
}

.quartos {
  margin-top: 14rem;
  width: 100%;
  height: 100%;
  z-index: 9999;
}

.slide-img {
  position: fixed;
  width: 100%;
  z-index: 0000;
  margin-top: 5rem;
}

.container-sis {
  margin-top: 4rem;
  text-align: center;
  font-size: 5rem;
  color: #4477ff;
}

.container-sis h6 {
  color: #000;
}

.title {
  font-style: bold;
  text-align: center;
  margin-top: 5rem;
}

.title h2 {
  color: #4477ff;
}

.menu-btn {
  margin-right: 0.05rem;
  margin-left: 0.05rem;
}

.number {
  padding-left: 5rem;
}

.select {
  border-radius: 15%;
}

.img-logo {
  text-align: left;
  margin: 1% 0 0 5%;
}

.img {
  height: 2rem;
  width: 5rem;
}

.right {
  text-align: right;
}

.menu-item {
  margin-right: 2.5rem;
}
</style>
