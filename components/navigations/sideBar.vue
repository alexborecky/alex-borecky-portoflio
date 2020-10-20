<template>
    <div class="burger-nav">
        <div class="open">
            <div class="flex middle" @click="isActive = !isActive" >
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M3 12H21M3 6H21M3 18H21" stroke="#1E1E1C" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
            </div> 
        </div>
      <transition name="fade">
        <div class="nav-container flex center-column-top" :class="{ passive: isActive }">
            <div class="container">
                <div class="close flex">
                    <div class="flex middle" @click="isActive = !isActive" >
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M18 6L6 18M6 6L18 18" stroke="#1E1E1C" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                    </div> 
                </div>
              <div class="mobile-links flex center-column-right">
                  <nuxt-link to="/" class="logo"> 
                        <img @click="isActive = !isActive" src="@/assets/images/logo.svg" alt="shoptetak.cz logo">
                    </nuxt-link>
                  <ul>
                      <li @click="isActive = !isActive"><nuxt-link to="/proces">Jaký je proces?</nuxt-link></li>
                      <li @click="isActive = !isActive"><nuxt-link to="/sluzby">Naše služby</nuxt-link></li>
                      <li @click="isActive = !isActive"><nuxt-link to="/o-nas">O nás</nuxt-link></li>
                      <li @click="isActive = !isActive"><a target="_blank" href="https://doplnky.shoptet.cz/katalog?partner=34">Doplňky</a></li>
                      <li @click="isActive = !isActive"><nuxt-link to="/kontakt">Kontakt</nuxt-link></li>
                  </ul>
              </div>
            </div>
        </div> 
      </transition>
    </div>
</template>

<script>


export default {
    name: 'sideBar',
    data () {
      return {
        isActive: true
      }
    },
    methods: {
    }
}
</script>



<style lang="scss">

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 1;
}

.passive {
  opacity: 0;
  z-index: -1000;
  height: 0vh;
  transform: translateX(100%) !important;
  position: absolute;
}

.open {
    width: 50%;
    float: right;
    z-index: 1000 !important;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    margin-top: 4px;
}



.burger-nav {
  z-index: 100;
  width: auto;
  @media only screen and (min-width: 450px) {
    display: none;
  }
  .nav-container {
    position: fixed;
    height: 120vh;
    top: 0 !important;
    background: linear-gradient(0deg, rgba(248,253,255,1) 0%, rgba(234,247,255,1) 100%);
    width: 110vw !important;
    z-index: 100;
    transition: .4s ease-in;
    transform: translateX(-90%);
    .close {
        height: 80px;
        justify-content: flex-end;
        align-items: center;
    }
  }
}


.mobile-links {
  display: flex; 
  justify-content: flex-end;
  text-align: right;
  height: 100%;
  padding: 0;
  text-align: center;
  .logo {
      img {
          height: 40px;
          margin-right: 24px;
        }
    }
    ul {
        margin-top: 32px;
        padding-left: 0;
        list-style-type: none;
        margin-right: 24px;
    a {
      margin-top: 24px;
      display: flex;
      justify-content: flex-end;
      text-decoration: none;
    }
  }
}


.nuxt-link-exact-active {
  color: $main-blue ;
}


@media only screen and (max-width: 960px) {
    .burger-nav {
        display: block;
    }
}

</style>
