<template>
  <section>
    <nav class="navbar pt-2 mx-6">
      <div
        class="BREADCRUMB breadcrumb has-succeeds-separator is-small is-size-7 has-text-weight-medium"
        aria-label="breadcrumbs"
      >
        <div>
          <ul>
            <li class="is-active">
              <a class="has-text-halo" href="#">
                <span>Pesanan</span>
              </a>
            </li>
            <li class="is-active">
              <a class="has-text-dark" href="#">
                <span>Pembayaran</span>
              </a>
            </li>
            <li class="is-active">
              <a class="has-text-dark" href="#">
                <span>Selesai</span>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- ---------------------NAVEND------------------- -->
    <section class="MAIN container mx-6">
      <div class="column">
        <div class="columns">
          <div class="column is-8 mr-6">
            <div class="container">
              <p class="title is-5 mb-5">Pesanan Anda</p>
            </div>
            <div class="columns mb-0 pb-0">
              <div class="column py-2">
                <div class="BORDER-TOP columns has-text-centered pb-0 mb-0">
                  <div class="column is-2 is-size-7 has-text-grey-light py-0">
                    Gambar
                  </div>
                  <div class="column is-size-7 has-text-grey-light py-0">
                    Deskripsi
                  </div>
                  <div class="column is-2 is-size-7 has-text-grey-light py-0">
                    Jumlah
                  </div>
                  <div class="column is-2 is-size-7 has-text-grey-light py-0">
                    Harga
                  </div>
                </div>
              </div>
            </div>
            <div class="card-pp" v-for="(item, i) in items" :key="i">
              <div class="container">
                <div class="columns is-vcentered">
                  <div class="column is-2 px-0">
                    <figure class="image">
                      <img :src="item.image" alt="" />
                    </figure>
                  </div>
                  <div class="column is-vcentered">
                    <div class="columns is-vcentered my-0">
                      <div class="column is-half py-0">
                        <p class="is-size-6 has-text-weight-semibold py-0">
                          Jokowi
                        </p>
                      </div>
                      <div class="column is-half py-0">
                        <p class="control" v-if="items.rating">
                          <b-rate :value="items.rating" show-score="disabled" />
                        </p>
                        <b-rate
                          v-model="rate"
                          :icon-pack="packs"
                          :icon="icons"
                          :max="maxs"
                          :size="sizes"
                          :locale="locale"
                          :show-score="score"
                          :custom-text="custom"
                          :show-text="text"
                          :texts="texts"
                          :rtl="isRtl"
                          :spaced="isSpaced"
                          :disabled="isDisabled"
                        ></b-rate>
                      </div>
                    </div>
                    <p class="is-size-7 has-text-weight-medium">
                      {{ item.title }}
                    </p>
                  </div>
                  <div class="JUMLAH column is-2 has-text-centered">
                    <div class="select">
                      <select>
                        <option>1</option>
                        <option>2</option>
                        <option>3</option>
                        <option>4</option>
                        <option>5</option>
                      </select>
                    </div>
                  </div>
                  <div class="column is-2 is-size-6 has-text-right px-0">
                    <p>Rp. 1.500.000</p>
                  </div>
                </div>
              </div>
              <div class="container">
                <div class="RINCIAN-PAKET container pb-3">
                  <div class="columns my-4 has-text-vcentered">
                    <div
                      class="column is-half is-size-5 has-text-weight-semibold has-text-left"
                    >
                      Paket Premium
                    </div>
                    <div
                      class="column is-half is-size-7 has-text-right has-text-weight-normal"
                    >
                      <a
                        class="has-text-halo"
                        v-if="!showMore"
                        @click="showMore = !showMore"
                        >Tampilkan rincian paket</a
                      >
                      <a
                        class="has-text-halo"
                        v-if="showMore"
                        @click="showMore = !showMore"
                        >Sembunyikan rincian paket</a
                      >
                    </div>
                  </div>
                  <div
                    class="container is-size-7 has-text-grey has-text-weight-medium"
                  >
                    <ul class="LIST columns is-multiline" v-if="showMore">
                      <li class="column is-one-quarter py-5">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 1</span>
                      </li>
                      <li class="column is-one-quarter py-5">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 2</span>
                      </li>
                      <li class="column is-one-quarter py-5">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 3</span>
                      </li>
                      <li class="column is-one-quarter py-5">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 4</span>
                      </li>
                      <li class="column is-one-quarter py-5">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 5</span>
                      </li>
                      <li class="column is-one-quarter py-5">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 6</span>
                      </li>
                      <li class="column is-one-quarter py-5">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 7</span>
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="CHECKOUT-PANEL column px-4 py-4 my-6">
            <section class="sidebar">
              <div class="card-py">
                <p class="is-size-4 pb-5"><strong>Ringkasan</strong></p>
                <div class="columns">
                  <div class="column is-size-6">Total sementara</div>
                  <div class="column has-text-right is-size-6">
                    <p>Rp. 1.500.000</p>
                  </div>
                </div>
                <div class="columns pb-4">
                  <div class="column is-size-6">Jumlah order (Hari)</div>
                  <div class="column is-one-third has-text-right is-size-6">
                    2
                  </div>
                </div>
                <div class="TEXT-TOTAL columns">
                  <div class="column is-3 is-size-6 pl-0">
                    <b>Total</b>
                  </div>
                  <div class="column has-text-right is-size-6 pr-0">
                    <b>Rp. 3.000.000</b>
                  </div>
                </div>
                <div class="buttons">
                  <b-button
                    tag="router-link"
                    to="/pembayaran"
                    type="is-halo"
                    expanded
                    >Checkout</b-button
                  >
                </div>
              </div>
            </section>
          </div>
        </div>
      </div>
    </section>
    <!-- ------------------------------------------------------ -->
  </section>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      isActive: false,
      showMore: false,

      rate: 4.6,
      maxs: 5,
      sizes: 'is-small',
      packs: 'mdi',
      icons: 'star',
      score: 'true',
      custom: '',
      text: false,
      texts: ['Very bad', 'Bad', 'Good', 'Very good', 'Awesome'],
      isRtl: false,
      isSpaced: false,
      isDisabled: true,
      locale: undefined, // Browser locale
      test: 0,
      items: [
        {
          title:
            'Some reason why my mouth have been silence in one of stopmoment',
          image:
            'https://cdna.artstation.com/p/assets/images/images/010/098/130/large/sajal-kr-chand-flat-landscape.jpg?1522574693',
          rating: 4.4,
        },
      ],
      // STEPS
      activeStep: 0,

      showSocial: false,
      isAnimated: true,
      isRounded: true,
      isStepsClickable: false,

      hasNavigation: true,
      customNavigation: false,
      isProfileSuccess: false,

      prevIcon: 'chevron-left',
      nextIcon: 'chevron-right',
      labelPosition: 'right',
      mobileMode: 'minimalist',
    }
  },
}
</script>
<style>
/* --------------HEADER to MAIN-------------- */
.sidebar {
  position: sticky;
}
.CHECKOUT-PANEL {
  border-style: solid;
  border-width: thin;
  height: fit-content;
  border-color: lightgrey;
  border-radius: 0.25rem;
}
.TEXT-TOTAL {
  border-top-style: solid;
  border-width: thin;
  border-color: lightgrey;
  margin: 0rem 0.25rem;
}
.BORDER-TOP {
  border-top-style: solid;
  border-width: thin;
  border-color: lightgrey;
}
a.dropdown-item.is-active,
.dropdown .dropdown-menu .has-link a.is-active,
button.dropdown-item.is-active {
  /* background-color: #7957d5; */
  /* color: #fff; */
}
.RINCIAN-PAKET {
  border-bottom-style: solid;
  border-width: thin;
  border-color: lightgrey;
}
.JUMLAH.button {
  padding-left: 1em;
  padding-right: 1em;
}
.LIST li {
  width: 30%;
}
.BREADCRUMB {
  margin: 0 auto;
}
.BREADCRUMB li {
  letter-spacing: 1.5px;
}
.MAIN {
  margin-bottom: 8rem;
}
.MAIN li {
  border-bottom-style: none;
}
</style>
