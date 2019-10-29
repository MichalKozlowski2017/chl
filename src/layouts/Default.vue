<template>
  <div class="layout">
    
      <header class="header">
        <g-link to="/"><g-image :alt="$static.metadata.siteName" src="../assets/images/logo.svg" height="90" /></g-link>
        <div class="header-info">
          <div class="header-info__info-1">
            CHL Holding Sp. z o. o.<br>
            ul. Jana Kazimierza 55<br>
            01-267 Warszawa
          </div>
          <div class="header-info__info-2">
            Tel. 22 560 50 03 / 22 560 51 76<br>
            Fax. 22 560 51 08<br>
            <a href="mailto:sekretariat.cashhandling@chlholding.pl ">sekretariat.cashhandling@chlholding.pl</a>
          </div>
        </div>
      </header>
    <transition name="fade" appear>
    <slot/>
    </transition>
    <footer>
      <div class="footer-info">
        <div class="footer-info__info-1 ">
          CHL Holding Sp. z o. o.<br>
          ul. Jana Kazimierza 55<br>
          01-267 Warszawa
        </div>
        <div class="footer-info__info-2 ">
          Tel. 22 560 50 03 / 22 560 51 76<br>
          Fax. 22 560 51 08<br>
          <a href="mailto:sekretariat.cashhandling@chlholding.pl ">sekretariat.cashhandling@chlholding.pl</a>
          
        </div>
      </div>
    </footer>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style lang="scss">
* {
    margin: 0;
    padding: 0;
}
.fade-enter-active,
.fade-leave-active {
    transition: opacity .5s
}

.fade-enter,
.fade-leave-to {
    opacity: 0
}
body {
  font-family: Poppins,Arial,sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
  color: $text-color;
  padding: 0 20px;
}

.layout {
  max-width: 1140px;
  margin: 0 auto;
  position: relative;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 90px;
  margin-top: 80px;
  margin-bottom: 60px;
  a {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
  }
}
.header-info {
  font-size: 16px;
  display: flex;
  font-weight: 500;
  padding-right: 10px;
  display: none;
  &__info-1 {
    width: 200px;
    margin-right: 20px;
  }
  a {
    color: $text-color;
    text-decoration: none;
    transition: 0.5s;
      &:hover {
        color: $primary;
      }
    }
}
.footer-info {
  text-align: center;
  display: block;
  div {
    padding: 13px;
  }
  a {
    color: $text-color;
    text-decoration: none;
    transition: 0.5s;
      &:hover {
        color: $primary;
      }
    }
}

@include mq($min-width: 768px) {
  .header {
    a {
      top: auto;
      position: relative;
      left: auto;
      transform: translateX(0);
    }
  }
  .header-info {
    display: flex;
  }
  .footer-info {
    display: none;
    
  }
}
.btn {
  position: relative;
  z-index: 1;
  cursor: pointer;
  button {
    cursor: pointer;
    background-color: transparent;
    border-radius: 2px;
    border: solid 2px #282828;
    padding: 7px 20px;
    margin: 15px 0;
    color: #fff;
    position: relative;

    &::after {
      content: '';
      position: absolute;
      top: 3px;
      left: 3px;
      width: 100%;
      height: 100%;
      border-radius: 2px;
      border: solid 2px $primary;
      background-color: $primary;
      z-index: -1;
      transition: 0.3s;
    }

    &:hover {
      &::after {
        top: 0;
        left: 0;
         border: solid 0px $primary;
         background-color: $primary;
      }
    }
  }
  
}


</style>
