<template>
  <div class="d-flex justify-content-between m-3">
    <div class="d-flex flex-wrap w-50 justify-content-evenly">
      <v-btn-toggle
        type="button"
        class="btn btn-success"
        @click="changeCategory(null)"
      >
        Все
      </v-btn-toggle>
      <v-btn-toggle
        type="button"
        class="btn btn-success"
        @click="changeCategory(54)"
      >
        Новости
      </v-btn-toggle>
      <v-btn-toggle
        type="button"
        class="btn btn-success"
        @click="changeCategory(55)"
      >
        События
      </v-btn-toggle>
      <v-btn-toggle
        type="button"
        class="btn btn-success"
        @click="changeCategory(56)"
      >
        Акции
      </v-btn-toggle>
    </div>
    <div>
      <form>
        <input
          class="form-control"
          v-model="search"
          type="text"
          placeholder="Search"
        />
      </form>
    </div>
  </div>

  <div class="d-flex flex-wrap justify-content-between items">
    <v-card
      class="mx-auto item"
      max-width="366"
      v-for="(item, index) in filterItems"
      :key="index"
    >
      <div class="card__img-items">
        <div class="card__img">
          <img :src="item.image_url" alt="rasm" />
        </div>
        <div class="new__type">
          <p class="new__type-text">
            {{ item.category_name }}
          </p>
        </div>
      </div>
      <v-card-text class="card_text">
        <h6 class="text--primary max-lines">{{ item.title }}</h6>

        <div class="description">
          <p>
            {{ item.description }}
          </p>
        </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
import { ref } from "vue";
import { $http } from "./plugins/axios";

export default {
  name: "App",

  data() {
    return {
      search: "",
      items: [],
      params: ref({
        page: 1,
        per_page: 6,
        last_page: null,
      }),
      filter: ref({
        category_id: null,
        word: null,
      }),
      btn_data: ["Все", "Новости", "События", "Акции"],
    };
  },

  async created() {
    try {
      await $http
        .get("news-page/news?page=1&per_page=9&word", {
          params: { per_page: this.params.per_page, page: this.params.page },
        })
        .then((res) => {
          this.items = res.data.data;
          console.log(this.items);
        });
    } catch (er) {
      console.log(er);
    }
  },

  methods: {
    changeCategory(id) {
      return this.items.filter(() => {
        return this.items.id === id;
      });
    },
  },
  computed: {
    filterItems() {
      return this.items.filter((item) => {
        return item.title.toLowerCase().includes(this.search.toLowerCase());
      });
    },
  },
};
</script>

<style>
.items {
  display: flex;
  flex-wrap: wrap;
}

.item {
  width: calc(100% / 3 - 20px);
  margin: 10px;
  border-radius: 15px;
  border: 1px solid #e5e5e5;
  /* padding-top: 20px; */
}

/* img */
.card__img-items {
  position: relative;
}

.card__img-items .card__img {
  overflow: hidden;
  height: 272px;
}

.card__img-items .card__img img {
  border-radius: 15px 15px 0 0;
  width: 100%;
  height: 100%;
  max-height: 272px;
  object-fit: cover;
  transition: 0.3s;
}

.card__img-items .card__img img:hover {
  border-radius: 15px 15px 0 0;
  cursor: pointer;
  transform: scale(1.1);
}

.card__img-items .new__type {
  position: absolute;
  top: calc(100% - 17px);
  background-color: #3c6;
  color: #fff;
  padding: 10px 20px;
  border-radius: 6px;
  left: 40px;
}

/*  */
.new__type {
  cursor: pointer;
}

.new__type-text {
  margin-bottom: 0 !important;
  font-size: 12px;
  line-height: 14px;
  letter-spacing: 0.1em;
  font-weight: 400;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
}

.max-lines {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.card_text {
  padding: 40px;
}

.card_text h6 {
  font-weight: 800;
  font-size: 22px;
  line-height: 28px;
  color: #303446;
}

.description {
  padding: 10px 0 0;
}

.description p {
  font-family: inherit;
  font-size: 16px;
  line-height: 26px;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  color: #aaa3bf;
}
</style>
