<template>
  <section>
    <div class="container is-fluid py-4">
      <div class="container mx-5">
        <nav
          class="breadcrumb has-arrow-separator mb-3 is-hidden-mobile"
          aria-label="breadcrumbs"
        >
          <ul>
            <li class="is-active has-text-weight-medium">
              <a href="#" aria-current="page">Kategori</a>
            </li>
          </ul>
        </nav>
      </div>
      <section class="main-content columns px-4 py-4">
        <aside class="column is-2 section">
          <!-- <p class="menu-label is-hidden-touch">General</p> -->
          <div class="content px-2 py-2">
            <b>Kategori</b>
            <p>----------------</p>
            <div class="field">
              <b-checkbox>Konsep Desain Rumah</b-checkbox>
            </div>
            <div class="field">
              <b-checkbox>Konsep Desain Gedung</b-checkbox>
            </div>
            <div class="field">
              <b-checkbox>Konsep Desain Taman</b-checkbox>
            </div>
            <div class="field">
              <b-checkbox>Konsep Desain Ruangan</b-checkbox>
            </div>
            <div class="field">
              <b-checkbox>Others</b-checkbox>
            </div>
          </div>
          <div class="content px-2 py-2">
            <b>Biaya</b>
            <p>----------------</p>
            <b-field>
              <b-input v-model="value" type="number"></b-input>
            </b-field>
            <b-field>
              <b-slider
                :min="20000"
                :max="2000000"
                aria-setsize="small"
                v-model="value"
                lazy
              ></b-slider>
            </b-field>
          </div>

          <div class="content px-2 py-2">
            <b>Level Mitra</b>
            <p>----------------</p>
            <div class="field">
              <b-checkbox>Mitra Baru</b-checkbox>
            </div>
            <div class="field">
              <b-checkbox>Mitra Level 1</b-checkbox>
            </div>
            <div class="field">
              <b-checkbox>Mitra Level 2</b-checkbox>
            </div>
            <div class="field">
              <b-checkbox>Top Mitra</b-checkbox>
            </div>
          </div>

          <div class="content px-2 py-2">
            <b>Tampilan Projek</b>
            <p>----------------</p>
            <div class="field">
              <b-checkbox>3D</b-checkbox>
            </div>
            <div class="field">
              <b-checkbox>Sket Pensil</b-checkbox>
            </div>
            <div class="field">
              <b-checkbox>Mapping</b-checkbox>
            </div>
            <div class="field">
              <b-checkbox>Others</b-checkbox>
            </div>
          </div>
        </aside>
        <div>
          <!-- class="content px-2 py-2" -->
          <section class="section">
            <div class="title is-3 mb-2 mx-4">
              <strong>Konsultan</strong>
            </div>
            <b-carousel-list v-model="test" :data="items" :items-to-show="4">
              <template slot="item" slot-scope="list">
                <div class="card CD-J">
                  <div class="card-image">
                    <figure class="image is-4by5">
                      <a :href="list.link"><img :src="list.image" /></a>
                    </figure>
                    <!-- <b-tag type="is-danger" rounded style="position: absolute; top: 0;"><b>50%</b></b-tag> -->
                  </div>
                  <div class="card-content">
                    <div class="content">
                      <div class="content columns mb-0 is-mobile">
                        <div class="column">
                          <div class="PHOTO-PROFILE container">
                            <img
                              src="https://raw.githubusercontent.com/AmzyZy24/Item/master/no-icon.png"
                              alt=""
                              width="100%"
                            />
                            <div class="DOT-STATUS container"></div>
                          </div>
                        </div>
                        <div class="INFO column is-full pl-1">
                          <div class="is-size-5 has-text-weight-semibold px-1">
                            <p class="title is-6">{{ list.title }}</p>
                          </div>
                          <div
                            class="is-one-fifth is-size-7 has-text-weight-normal px-1"
                          >
                            Mitra level <span>2</span>
                          </div>
                        </div>
                      </div>
                      <div class="content columns mb-0 is-mobile">
                        <div class="column">
                          <p class="subtitle is-7">
                            Make your dreams come true and standing apart on
                            this imagination
                          </p>
                        </div>
                      </div>
                      <div class="field name-mr is-grouped mb-2 is-mobile">
                        <p class="control" v-if="list.rating">
                          <b-rate
                            :value="list.rating"
                            show-score
                            disabled
                            :max="maxs"
                            :v-show="score"
                          >
                          </b-rate>
                        </p>
                        <p>(23 reviews)</p>
                      </div>
                      <div class="field is-grouped is-mobile">
                        <p class="control" style="margin-right: auto;">
                          <button class="button is-small is-danger is-outlined">
                            <b-icon size="is-small" icon="heart" />
                          </button>
                        </p>
                        <p class="cotent" style="margin-left: auto;">
                          Price Start = $23
                        </p>
                      </div>
                    </div>
                  </div>
                </div>
              </template>
            </b-carousel-list>
            <div class="title is-3 mb-2 mt-4 mx-2 px-2">
              <strong>Jasa</strong>
            </div>
            <b-carousel-list
              v-model="carousel2"
              :data="items"
              :items-to-show="4"
            >
              <template slot="item" slot-scope="list">
                <div class="card CD-J">
                  <div class="card-image">
                    <figure class="image is-4by5">
                      <a @click="list.index;"><img :src="list.image" /></a>
                    </figure>
                    <!-- <b-tag type="is-danger" rounded style="position: absolute; top: 0;"><b>50%</b></b-tag> -->
                  </div>
                  <div class="card-content">
                    <div class="content">
                      <div class="content columns mb-0 is-mobile">
                        <div class="column">
                          <div class="PHOTO-PROFILE container">
                            <img
                              src="https://raw.githubusercontent.com/AmzyZy24/Item/master/no-icon.png"
                              alt=""
                              width="100%"
                            />
                            <div class="DOT-STATUS container"></div>
                          </div>
                        </div>
                        <div class="INFO column is-full pl-1">
                          <div class="is-size-5 has-text-weight-semibold px-1">
                            <p class="title is-6">{{ list.title }}</p>
                          </div>
                          <div
                            class="is-one-fifth is-size-7 has-text-weight-normal px-1"
                          >
                            Mitra level <span>2</span>
                          </div>
                        </div>
                      </div>
                      <div class="content columns mb-0 is-mobile">
                        <div class="column">
                          <p class="subtitle is-7">
                            Make your dreams come true and standing apart on
                            this imagination
                          </p>
                        </div>
                      </div>
                      <div class="field name-mr is-grouped mb-2 is-mobile">
                        <p class="control" v-if="list.rating">
                          <b-rate
                            :value="list.rating"
                            show-score
                            disabled
                            :max="maxs"
                            :v-show="score"
                          >
                          </b-rate>
                        </p>
                        <p>(23 reviews)</p>
                      </div>
                      <div class="field is-grouped is-mobile">
                        <p class="control" style="margin-right: auto;">
                          <button class="button is-small is-danger is-outlined">
                            <b-icon size="is-small" icon="heart" />
                          </button>
                        </p>
                        <p class="cotent" style="margin-left: auto;">
                          Price Start = $23
                        </p>
                      </div>
                    </div>
                  </div>
                </div>
              </template>
            </b-carousel-list>
            <div class="SHOW-MORE buttons py-5">
              <button
                class="button is-small is-fullwidth has-text-weight-medium"
              >
                Lihat Lebih Banyak
                <a class="card-header-icon">
                  <b-icon :icon="'menu-down'"> </b-icon>
                </a>
              </button>
            </div>
          </section>
        </div>
      </section>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      isCard2ModalActive: false,
      isCardModalActive: false,
      value: 20,
      score: 'true',
      maxs: 1,
      test: 0,
      carousel2: 0,
      isActive: false,
      items: [
        {
          title: 'Slide 1',
          image:
            'https://upload.wikimedia.org/wikipedia/commons/f/f5/Poster-sized_portrait_of_Barack_Obama.jpg',
          rating: 4.4,
          link: '/mitra',
        },
        {
          title: 'Slide 2',
          image:
            'https://images.unsplash.com/photo-1546538994-4f15d0aa966f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&w=1000&q=80',
          rating: 3.5,
          link: '/mitra',
        },
        {
          title: 'Slide 3',
          image: 'https://jooinn.com/images/portrait-1.jpg',
          rating: 5,
          link: '/mitra',
        },
        {
          title: 'Slide 1',
          image:
            'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQCRyi4-dicSyWEFp0un3Taue0spzl0b6fNQA&usqp=CAU',
          rating: 4.4,
          link: '/mitra',
        },
        {
          title: 'Slide 2',
          image: 'https://i.redd.it/7mkdr70e1dl31.jpg',
          rating: 3.5,
          link: '/mitra',
        },
        {
          title: 'Slide 3',
          image:
            'https://www.zarias.com/wp-content/uploads/2015/08/Portrait-Photography-Tips-and-Ideas-261.jpg',
          rating: 5,
          link: '/mitra',
        },
        {
          title: 'Slide 1',
          image:
            'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQCRyi4-dicSyWEFp0un3Taue0spzl0b6fNQA&usqp=CAU',
          rating: 4.4,
          link: '/mitra',
        },
        {
          title: 'Slide 2',
          image: 'https://i.redd.it/7mkdr70e1dl31.jpg',
          rating: 3.5,
          link: '/mitra',
        },
        {
          title: 'Slide 3',
          image:
            'https://www.zarias.com/wp-content/uploads/2015/08/Portrait-Photography-Tips-and-Ideas-261.jpg',
          rating: 5,
          link: '/mitra',
        },
      ],
    }
  },
}
</script>
<style>
li {
  border-bottom-style: ridge;
  border-color: hsl(0, 0%, 86%);
  border-width: thin;
  padding-bottom: 0.5rem;
}
/* --------------css mid------------- */
.b-slider.is-primary .b-slider-fill {
  background: #f79651 !important;
}
.menu-list a.is-active {
  background-color: #f79651;
  color: #fff;
}
.menu-list a:hover {
  background-color: #f7965126;
  color: #363636;
}
.section {
  padding: 1rem 1rem;
}
article,
aside,
figure,
footer,
header,
hgroup,
section {
  display: grid;
}
body {
  font-size: small;
}
.icon-f img {
  padding: 10px;
}
.a1 img {
  width: 240px;
  height: auto;
  padding: 4px;
}
/* --------------css index------------- */
.carousel-list .carousel-slides .carousel-slide {
  border: 2px solid transparent;
  -ms-flex-negative: 0;
  flex-shrink: 0;
  padding: 1%;
}
.card-content {
  background-color: transparent;
  padding: 0.5rem;
}
.DOT-STATUS {
  width: 8px;
  height: 8px;
  background-color: greenyellow;
  border-radius: 290486px;
  position: absolute;
  bottom: 1px;
  right: 1px;
}
.PHOTO-PROFILE {
  width: 2.7rem;
  height: 2.7rem;
  border-color: #f79351;
  border-width: thin;
  border-style: solid;
  border-radius: 290486px;
}
</style>
