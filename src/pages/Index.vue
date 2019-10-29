<template>
  <Layout>
    <div class="wrapper">
      <!-- Learn how to use images here: https://gridsome.org/docs/images -->
      <transition name="fade">
      <div id="notification" class="notification" v-if="showNotification">
        <div class="notification__close" @click="showNotification = !showNotification">x</div>
        <p>
          Zmieniamy się dla Was! Pełna wersja serwisu w przygotowaniu.
        </p>
      </div>
      </transition>
      <div class="content-wrapper">
        <div class="content-wrapper__left">
          <h1>
            CHL Holding to grupa spółek wyspecjalizowanych w kompleksowej obsłudze logistyki gotówki. 
          </h1>
          <g-image alt="image" src="../assets/images/obrazek@2x.jpg" />
        </div>
        <div class="content-wrapper__right">
          <div class="paragraph">
            Oferujemy usługi w zakresie transportu i obsługi gotówki. Jeśli gotówka odgrywa znaczącą rolę w Twoim biznesie, jesteśmy przygotowani do jej obsługi od odbioru, przez transport, liczenie 
i sortowanie, do uznania Twojego rachunku w formie elektronicznej. 
          </div>
          <div class="paragraph">
           Nasze usługi świadczymy dla banków i innych instytucji finansowych, operatorów bankomatów, sieci handlowych 
i usługowych oraz jednostek administracji publicznej. Dzięki ogólnopolskiej sieci sortowni pieniędzy i baz transportowych, 
a także największej flocie nowoczesnych bankowozów w Polsce, jesteśmy w stanie zapewnić usługi wysokim poziomie jakościowym, gdziekolwiek znajduje się Twój oddział banku, bankomat, sklep czy punkt usługowy.
          </div>
          <div class="paragraph">
           Jesteśmy liderem nowoczesnych rozwiązań w obsłudze gotówki 
w Twoim punkcie kasowym. Mając na względzie wygodę 
i bezpieczeństwo Twoich pracowników oraz konieczność szybkiego uznania Twojego rachunku proponujemy rozwiązanie Inteligent Safe Service, oparte na innowacyjnym wpłatomacie CHL, dzięki któremu gotówka będzie zawsze pod Twoją kontrolą.
          <br>
          <br>
          Zapraszamy do kontaktu: 
<a href="mailto:cash.handling@chlholding.pl">cash.handling@chlholding.pl</a>
          </div>

          <div class="downloads">
            <div class="downloads__item">
              <p>Polityka prywatności</p>
              <a href="CHL_Holding_Polityka_prywatnosci.pdf" target="_blank" class="btn">
                <button>
                  Pobierz dokument
                </button>
              </a>
            </div>
            <div class="downloads__item">
              <p>Zasady powierzania i&nbsp;udostępniania danych</p>
              <a href="CHL_Holding_Zasady_powierzania_i_udostepniania_danych.pdf" target="_blank" class="btn">
                <button>
                  Pobierz dokument
                </button>
              </a>
            </div>
          </div>
        </div>
      </div>
      

      
    </div>
    



  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'CHL Holding'
  },
  data() {
    return { 
      showNotification: true 
    }
  }

}
</script>

<style lang="scss">
.wrapper {
  transition: 0.5s;
}
.notification {
  background-color: $primary;
  font-weight: 600;
  padding: 20px;
  color: #fff;
  position: relative;
  &__close {
    width: 25px;
    height: 25px;
    position: absolute;
    text-align: center;
    top: 6px;
    right: 6px;
    cursor: pointer;
  }
}

.content-wrapper {
  display: flex;
  flex-direction: column;

  h1 {
    font-size: 24px;
    text-align: center;
  }
  img {
    position: relative;
    width: 70%;
    margin: 30px 0;
  }
  &__left, &__right {
    
    width: 100%;
  } 
  &__left {
    display: flex;
    padding: 20px 0;
    flex-direction: column;
    align-items: center;
  }
}

.paragraph {
  font-size: 16px;
  padding: 20px;
  a {
    text-decoration: none;
    color: $primary;
    &:hover {
      text-decoration: underline;
    }
  }
}

.downloads {
    padding: 20px;

  &__item {
    padding: 20px 0;
    text-align: center;
    &:not(:first-child) {
      border-top: solid 2px #f4f4f4;
    }
    p {
      width: 200px;
      margin: 0 auto;
      color: #787878;
      font-weight: 600;
    }
  }
}

@include mq($min-width: 768px) {
  .notification {
    font-size: 25px;
    letter-spacing: -0.1px;
    line-height: 1;
    padding: 20px 40px;
    &__close {
      font-size: 20px;
    }
  }
  .downloads {
    padding: 20px;
     &:not(:first-child) {
        &::after {
          content: '';
          width: 100%;
          height: 2px;
          background-color: #f4f4f4;
        }
      }
    &__item {
      text-align: left;
      display: flex;
      justify-content:space-between;
      width: 100%;
      position: relative;
     
      a {
        margin: 0;
        position: absolute;
        right: 0;
        top: 45%;
        transform: translateY(-50%);
      }
      p {
        width: 50%;
        max-width: 200px;
        margin: 0;
        color: #787878;
      }
    }
  }
  .content-wrapper {
    display: flex;
    flex-direction: row; 
    padding: 30px 0;
    h1 {
      font-size: 32px;
      text-align: center;
    }
    img {
      position: relative;
      width: 90%;
      margin: 30px 0;
    }
  }
}
@include mq($min-width: 1024px) {
  .notification {
    font-size: 32px;
  }
}
</style>
