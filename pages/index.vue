<template>
  <section>
    <!-- ------------------------------------------------NAVER---------------------------------------------------------- -->

    <section class="TOP section py-6 px-3 mx-6">
      <div class="SEARCH container">
        <div class="title is-3 has-text-centered">
          Menjelajahi Negeri Bersama Kami
        </div>
        <div class="SEARCH-BOX container has-text-centered">
          <b-field>
            <!-- crash dengan carousel -->
            <b-input
              placeholder="Pencarian . . ."
              type="search"
              icon-right="magnify"
              icon-right-clickable="search"
            >
            </b-input>
          </b-field>
        </div>
      </div>

      <div class="POPULER container mt-6">
        <div class="title is-5 ml-6">
          Paling populer saat ini
        </div>
        <div class="CAROUSEL">
          <b-carousel-list
            v-model="test"
            :data="items"
            :items-to-show="4"
            :arrow-hover="arrowHover"
            :repeat="repeat"
            class="CAROUSEL-LIST is-shadowless"
          >
            <template slot="item" slot-scope="list">
              <div class="card mx-2">
                <div class="card-image">
                  <figure class="image is-4by5">
                    <a href="/mitra"><img :src="list.image" /></a>
                  </figure>
                </div>
              </div>
            </template>
          </b-carousel-list>
        </div>
      </div>
    </section>
    <section class="BOTTOM section py-6 px-3 mx-6">
      <div class="columns">
        <div class="column is-one-fifth">
          <div class="container title is-4 has-text-weight-bold">
            Kategori
          </div>
          <div class="KATEGORI-LIST title is-6">
            <aside>
              <a href="/kategori" class="has-text-grey-dark">Konsultan</a><br />
              <a href="/kategori" class="has-text-grey-dark">Persewaan</a><br />
              <a href="/kategori" class="has-text-grey-dark">Produsen</a><br />
              <a href="/kategori" class="has-text-grey-dark">Tenaga</a><br />
              <a href="/kategori" class="has-text-grey-dark">Jasa</a><br />
              <a href="/kategori" class="has-text-grey-dark">Toko</a>
            </aside>
          </div>
        </div>
        <div class="column is-two-thirds pt-5">
          <div class="container pt-4">
            <div class="title is-4 has-text-weight-bold mb-3">
              <p>
                Jasa
                <span class="title is-6 has-text-weight-medium"
                  ><span>100</span> Mitra</span
                >
              </p>
            </div>
            <div class="columns is-mobile">
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
            </div>
          </div>
          <div class="container pt-4">
            <div class="title is-4 has-text-weight-bold mb-3">
              <p>
                Toko
                <span class="title is-6 has-text-weight-medium"
                  ><span>500</span> Mitra</span
                >
              </p>
            </div>
            <div class="columns is-mobile">
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
            </div>
          </div>
          <div class="container pt-4" v-if="seeMore">
            <div class="title is-4 has-text-weight-bold mb-3">
              <p>
                Produsen
                <span class="title is-6 has-text-weight-medium"
                  ><span>500</span> Mitra</span
                >
              </p>
            </div>
            <div class="columns is-mobile">
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
            </div>
          </div>
          <div class="container pt-4" v-if="seeMore">
            <div class="title is-4 has-text-weight-bold mb-3">
              <p>
                Konsultan
                <span class="title is-6 has-text-weight-medium"
                  ><span>500</span> Mitra</span
                >
              </p>
            </div>
            <div class="columns is-mobile">
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
              <div class="column is-one-third">
                <figure class="image is-4by3">
                  <a
                    ><img
                      src="https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true"
                      alt=""
                  /></a>
                </figure>
              </div>
            </div>
          </div>
          <div
            class="button is-small is-fullwidth my-5"
            v-if="!seeMore"
            @click="seeMore = true"
          >
            <strong>Lihat lebih banyak</strong>
            <a class="card-header-icon">
              <b-icon :icon="'menu-down'"> </b-icon>
            </a>
          </div>
        </div>
      </div>
    </section>
  </section>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
      isCard2ModalActive: false,
      isCardModalActive: false,
      seeMore: false,

      arrow: true,
      arrowHover: false,
      drag: true,
      gray: false,
      opacity: false,
      values: 1,
      perList: 4,
      increment: 1,
      repeat: true,
      items: [
        {
          title: 'Slide 1',
          image:
            'https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true',
        },
        {
          title: 'Slide 2',
          image:
            'https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true',
        },
        {
          title: 'Slide 3',
          image:
            'https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true',
        },
        {
          title: 'Slide 4',
          image:
            'https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true',
        },
        {
          title: 'Slide 5',
          image:
            'https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true',
        },
        {
          title: 'Slide 6',
          image:
            'https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true',
        },
        {
          title: 'Slide 7',
          image:
            'https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true',
        },
        {
          title: 'Slide 8',
          image:
            'https://github.com/amzy24/Item/blob/master/no-image-block.png?raw=true',
        },
      ],
    }
  },
}
</script>

<style>
.SEARCH-BOX {
  max-width: 60%;
  border-radius: 10px;
}
.SEARCH-BOX input {
  border-radius: 7px;
  border-width: thin;
  border-color: hsl(0, 0%, 29%);
}
.card img {
  border-radius: 1rem;
}
.CAROUSEL-LIST {
  width: 92%;
  margin: 0 auto;
}
.carousel-list {
  position: static;
}
.mdi-chevron-right.mdi-24px.mdi:before,
.mdi-chevron-left.mdi-24px.mdi:before {
  font-size: 125px;
}
.carousel-arrow .icon {
  background: none;
  color: hsl(0, 0%, 71%);
  cursor: pointer;
  border: none;
  border-radius: none;
  outline: 0;
}
.carousel-arrow .icon:hover {
  color: hsl(0, 0%, 10%);
  border: none;
  opacity: 0.5;
}
.carousel-arrow .icon.has-icons-right {
  right: -0.5rem;
  top: 60%;
}
.carousel-arrow .icon.has-icons-left {
  left: -0.5rem;
  top: 60%;
}
.TOP {
  border-bottom-style: solid;
  border-color: hsl(0, 0%, 86%);
  border-bottom-width: thin;
}
.KATEGORI-LIST {
  line-height: 2rem;
}
.KATEGORI-LIST a:hover {
  border: hsl(0, 0%, 71%);
  opacity: 0.5;
}
figure img {
  border-radius: 10px;
}
.SHOW-MORE .button {
  border-radius: 8px;
  border-width: none;
  border-color: hsl(0, 0%, 80%);
}
/* -------------RESPONSIVE--------------- */
@media screen and (max-width: 768px) {
  .TOP {
    margin-left: 0.25rem !important;
    margin-right: 0.25rem !important;
  }
  .BOTTOM {
    margin-left: 0.25rem !important;
    margin-right: 0.25rem !important;
  }
  .carousel-arrow {
    visibility: hidden;
  }
  .card img {
    border-radius: 0.25rem;
  }
  .button.is-halo {
    border-radius: 5px;
  }
  figure img {
    border-radius: 5px;
  }
}
</style>
