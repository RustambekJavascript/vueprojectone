<template>
  <v-container>
    <!-- navbar -->
    <v-row no-gutters class="navbar">
      <!-- icon -->
      <v-col cols="12" sm="6" md="2">
        <img src="../images/allin.svg" />
      </v-col>
      <!-- menu list -->
      <v-col cols="12" sm="6" md="8">
        <v-menu>
          <v-list>
            <v-list-item
              v-for="(list, index) in lists"
              :key="index"
              :value="index"
              class="list_item"
            >
              <v-list-item-title>
                <a href="#">{{ list.title }} </a>
              </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-col>
      <!-- end menu -->
      <v-col cols="12" sm="6" md="2" class="menu_end">
        <v-select
          v-model="select"
          :hint="`${select.state}, ${select.abbr}`"
          :items="items"
          item-text="state"
          item-value="abbr"
          label="Select"
          persistent-hint
          return-object
          single-line
        ></v-select>
        <v-btn type="button" class="btn">Отслеживание </v-btn>
      </v-col>
    </v-row>
    <!-- Курьерская служба All-in Delivery section -->
    <v-main>
      <section class="one_section">
        <v-container>
          <div class="main-banner__wrap">
            <div class="main-banner_content">
              <h1>Курьерская служба All-in Delivery</h1>
              <p>
                Добро пожаловать в курьерскую службу All-in Delivery! Мы
                доставим любые ваши отправления по Ташкенту, Узбекистану и всему
                миру экспресс-почтой!
              </p>
              <div class="btn_group_link">
                <v-btn type="button" class="btn" style="margin-left: 0"
                  >Отслеживание
                </v-btn>
                <a href="#" class="obr"> Обратная связь </a>
              </div>
            </div>
          </div>
        </v-container>
        <div class="main-banner_bottom">
          <v-container>
            <div class="main-banner__details">
              <div
                class="main-banner__details-item"
                v-for="(banner, index) in banners"
                :key="{ index }"
              >
                <p class="banner_title">{{ banner.title }}</p>
                <p class="banner_text">{{ banner.text }}</p>
              </div>
            </div>
          </v-container>
        </div>
      </section>
      <section class="two_section">
        <div class="about">
          <div class="about__column">
            <h1>Курьерская служба All-in Delivery</h1>
            <h4>
              «All-in Delivery» - предлагает выгодные условия партнерства,
              оптимальные тарифы, а также сервис высокого уровня
            </h4>
            <p>
              Наша МИССИЯ – формирование и совершенствование курьерской службы
              как части масштабной транспортной логистики Узбекистана. Мы делаем
              сервис банальным и комфортным для наши клиентов, увеличивая
              эффективность, комфорт, доступность курьерских услуг.
            </p>
            <v-btn
              type="button"
              class="btn"
              style="padding: 15px 30px; margin-left: 0"
              >Узнать больше
            </v-btn>
            <!-- <ButtonV>Hello</ButtonV> -->
          </div>
          <div class="about__photo">
            <div class="about__photo-container">
              <div class="about__photo-main">
                <img src="../images/usta.png" alt="No img" />
              </div>
              <div class="about__photo-secondary">
                <img src="../images/usta.png" alt="No img" />
              </div>
              <div class="about__photo-info">
                <div class="about__photo-info-inner">
                  <p class="font-weight-regular">15350 +</p>
                  <p>Доставлено товаров</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <!-- slider artel -->
    </v-main>
  </v-container>
</template>

<script>
export default {
  name: "LayoutP",

  data() {
    return {
      lists: [
        { title: "Главная" },
        { title: "Тарифы и услуги" },
        { title: "Новости" },
        { title: "Зона покрытия" },
        { title: "О нас" },
        { title: "Контакты" },
      ],
      select: { state: "Florida", abbr: "FL" },
      items: [
        { state: "Florida", abbr: "FL" },
        { state: "Georgia", abbr: "GA" },
        { state: "Nebraska", abbr: "NE" },
        { state: "California", abbr: "CA" },
        { state: "New York", abbr: "NY" },
      ],
      banners: [
        { title: "50 +", text: "Заказов в день" },
        { title: "1500 +", text: "Заказов в месяч" },
        { title: "20 +", text: "Сотрудников в компании" },
        { title: "6000 +", text: "Довольных клиентов" },
      ],
    };
  },
};
</script>

<style scoped>
:root {
  --weight4: 400;
  --weight5: 500;
  --weight6: 600;
  --weight7: 700;
  --weight8: 800;
  --color-main: #3c6;
  --color-dark: #303446;
  --color-text: #aaa3bf;
  --color-bg: #f6f5f9;
  --color-info-bg: #e4fbec;
  --color-border: #e5e5e5;
  --line-height25: 25px;
}
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-around;
}

.list_item {
  padding: 5px;
  margin: 14px 12px;
}

v-list-item-title a {
  color: #bbbcc2;
  font-size: 14px;
  font-weight: 600;
}

v-list-item-title a:hover {
  color: #000;
}

a {
  text-decoration: none;
}

.btn {
  color: white;
  background-color: #33cc66;
  cursor: pointer;
  padding: 0 30px;
  height: 50px;
  line-height: 50px;
  border-radius: 10px;
  margin-left: 40px;
}

.menu_end {
  display: flex;
  align-items: center;
  justify-content: center;
}

v-main {
  height: 100vh;
  width: 100vw;
}

v-main .one_section {
  background: url("../images/usta.png") no-repeat;
  background-size: cover;
  height: 100vh;
  width: 100%;
  margin-bottom: 200px;
}

/* main_banner_bottom */
.main-banner_bottom {
  backdrop-filter: blur(30px);
  margin-top: -90px;
}

.main-banner_content p {
  line-height: 41px;
  font-weight: 700;
  font-size: calc(var(--font, 16) / 16 * 1rem);
}

.main-banner_content h1 {
  line-height: 50px;
  font-weight: 700;
  font-size: 42px;
}

.main-banner__details {
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-gap: 20px;
  text-align: center;
  align-items: center;
  justify-content: center;
  color: #fff;
  min-height: 190px;
  width: 100%;
}

.main-banner__wrap {
  margin-left: 40px;
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
  color: #fff;
}

.main-banner_content {
  max-width: 450px;
  width: 100%;
}

.btn_group_link {
  display: flex;
  align-items: flex-end;
}

.btn_group_link a {
  margin-left: 20px;
  margin-bottom: 10px;
  color: white;
  padding-bottom: 2px;
  border-bottom: 2px solid white;
  font-size: 16px;
}

.banner_title {
  font-size: 34px;
  font-weight: 700;
  line-height: 41px;
}

.banner_text {
  font-size: 14px;
  line-height: 24px;
  color: #000;
}

/* two section */
.about {
  display: grid;
  grid-template-columns: 1fr 1.8fr;
  align-items: center;
  grid-gap: 100px;
  width: 100%;
  margin-bottom: 200px;
}

.about div {
  margin-left: 40px;
}

.about__photo-container {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.about__photo-main {
  max-width: 410px;
  width: 100%;
  max-height: 480px;
  height: 100%;
  border-radius: 14px;
  overflow: hidden;
  margin-left: 70px;
}

.about__photo-main img {
  object-fit: cover;
  width: 100%;
  height: 480px;
}

.about__photo-secondary {
  position: absolute;
  left: 0;
  bottom: -100px;
  max-width: 297px;
  width: 100%;
  border-radius: 14px;
  overflow: hidden;
}

.about__photo-secondary img {
  width: 100%;
  height: 377px;
  -o-object-fit: cover;
  object-fit: cover;
}

.about__photo-info {
  position: absolute;
  bottom: -70px;
  right: -5px;
  padding: 30px;
  background-color: #33cc66;
  color: #fff;
  border-radius: 0 14px 14px 14px;
}

.about__photo-info-inner {
  position: relative;
}

.about__photo-info-inner:before {
  content: "";
  position: absolute;
  border-left: 0 solid transparent;
  border-bottom: 35px solid transparent;
  border-right: 33px solid #33cc66;
  border-top: 0 solid transparent;
  line-height: 0;
  left: -102px;
  top: -50px;
}
</style>
