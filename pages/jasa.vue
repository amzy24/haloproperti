<template>
  <section class="ROOT section px-0 py-0">
    <section class="HEADER section py-5 px-3 mx-6">
      <nav class="navbar" role="navigation" aria-label="main navigation">
        <div class="navbar-brand">
          <a class="navbar-item" href="/">
            <img src="~/assets/logo-halo.png" width="150" />
          </a>

          <a
            role="button"
            class="navbar-burger burger"
            aria-label="menu"
            aria-expanded="false"
            data-target="navbarBasicExample"
          >
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
          </a>
        </div>

        <div id="navbarBasicExample" class="navbar-menu">
          <div class="navbar-start">
            <b-field class="py-2 pl-4">
              <b-input
                placeholder="Pencarian . . . "
                type="search"
                icon-right="magnify"
                icon-right-clickable="search"
              >
              </b-input>
            </b-field>
          </div>

          <div class="navbar-end">
            <div class="navbar-item">
              <div class="buttons">
                <a class="button is-light">
                  <strong>Gabung Mitra</strong>
                </a>
                <a class="button is-halo">
                  Masuk
                </a>
              </div>
            </div>
          </div>
        </div>
      </nav>
    </section>
    <section class="MAIN-TOP section pt-5 pb-6 px-3 mx-6">
      <div class="container">
        <div class="columns is-vcentered box">
          <div class="column is-one-quarter">
            <div class="container pr-1">
              <div class="PHOTO-PROFILE container">
                <img
                  src="https://raw.githubusercontent.com/AmzyZy24/Item/master/no-icon.png"
                  alt=""
                  width="100%"
                />
                <div class="DOT-STATUS container"></div>
              </div>
              <div class="mt-2 has-text-centered">
                <a class="is-size-7" href="">Ubah foto</a>
              </div>
            </div>
          </div>
          <div class="column columns mx-5 has-text-weight-semibold">
            <div class="column has-text-weight-medium">
              <div class="container my-4 is-size-6">Ramzy123</div>
              <div class="container my-4 is-size-6">Mitra Level 1</div>
            </div>
            <div class="column has-text-weight-medium">
              <div class="container my-4 is-size-6">Kediri</div>
              <div class="container my-4 is-size-6">10 Total Pesanan</div>
            </div>
            <div class="column has-text-weight-medium">
              <div class="container my-4 is-size-6">Bergabung Tahun 2020</div>
              <div class="RATING my-4 is-size-5">
                <b-rate
                  v-model="rating.rate"
                  :icon-pack="rating.packs"
                  :icon="rating.icons"
                  :max="rating.maxs"
                  :size="rating.sizes"
                  :locale="rating.locale"
                  :show-score="rating.score"
                  :custom-text="rating.custom"
                  :rtl="rating.isRtl"
                  :spaced="rating.isSpaced"
                  :disabled="rating.isDisabled"
                >
                </b-rate>
              </div>
            </div>
          </div>
        </div>
        <div class="columns">
          <div class="column is-one-quarter">
            <div class="sidebar-page">
              <section class="sidebar-layout">
                <b-sidebar
                  position="static"
                  :mobile="mobile"
                  :expand-on-hover="expandOnHover"
                  :reduce="reduce"
                  type="is-light"
                  open
                >
                  <div class="p-1">
                    <b-menu class="is-custom-mobile">
                      <b-menu-list label="Akun">
                        <b-menu-item label="Profile"> </b-menu-item>
                        <b-menu-item label="Password"></b-menu-item>
                        <b-menu-item label="Pesanan Saya"></b-menu-item>
                      </b-menu-list>
                      <b-menu-list label="Mitra">
                        <b-menu-item active label="Jasa"></b-menu-item>
                        <b-menu-item label="Orderan"></b-menu-item>
                      </b-menu-list>
                      <b-menu-list label="Actions">
                        <b-menu-item label="Logout"></b-menu-item>
                      </b-menu-list>
                    </b-menu>
                  </div>
                </b-sidebar>
              </section>
            </div>
          </div>
          <div class="column mx-5 px-5">
            <div class="container">
              <div class="container my-5 is-size-4">Jasa</div>
              <div class="container">
                <div class="card-pp" v-for="(item, i) in items" :key="i">
                  <div class="container">
                    <div class="columns is-vcentered box">
                      <div class="column is-2 px-0">
                        <figure class="image">
                          <img :src="item.image" alt="" />
                        </figure>
                      </div>
                      <div class="column">
                        <p class="is-size-6 has-text-weight-medium">
                          {{ item.title }}
                        </p>
                      </div>
                      <div class="field has-text-centered">
                        <div class="container">{{ isSwitchedCustom }}</div>
                        <div class="container is-centered ml-5">
                          <b-switch
                            v-model="isSwitchedCustom"
                            true-value="Aktif"
                            false-value="Tidak Aktif"
                            type="is-success"
                          >
                          </b-switch>
                        </div>
                      </div>
                    </div>
                    <div class="columns is-vcentered box">
                      <div class="column is-2 px-0">
                        <figure class="image">
                          <img :src="item.image" alt="" />
                        </figure>
                      </div>
                      <div class="column">
                        <p class="is-size-6 has-text-weight-medium">
                          {{ item.title }}
                        </p>
                      </div>
                      <div class="field has-text-centered">
                        <div class="container">{{ isSwitchedCustom }}</div>
                        <div class="container is-centered ml-5">
                          <b-switch
                            v-model="isSwitchedCustom"
                            true-value="Aktif"
                            false-value="Tidak Aktif"
                            type="is-success"
                          >
                          </b-switch>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="container">
              <div class="container my-5 is-size-4">Orderan</div>
              <div class="columns">
                <div class="card-pp column" v-for="(item, i) in items" :key="i">
                  <div class="container">
                    <div class="columns is-vcentered box">
                      <div class="column">
                        <div class="columns container">
                          <div class="column is-2 px-0">
                            <figure class="image">
                              <img :src="item.image" alt="" />
                            </figure>
                          </div>
                          <div class="column">
                            <p class="is-size-6 has-text-weight-medium">
                              {{ item.title }}
                            </p>
                          </div>
                        </div>
                        <div class="columns container is-size-7">
                          <div class="column is-3">
                            <p>Alamat</p>
                            <p>Tanggal Pelaksanaan</p>
                            <p>Tanggal Order</p>
                            <p>Paket</p>
                            <p>Biaya</p>
                          </div>
                          <div class="column">
                            <p>
                              :
                              <span
                                >Perum Doko Indah Blok C18 Kota Kediri Jawa
                                Timur</span
                              >
                            </p>
                            <p>
                              : <span>13-10-2020 s/d 14-10-2020 (2 hari)</span>
                            </p>
                            <p>: <span>12-09-2020</span></p>
                            <p>: <span>Premium</span></p>
                            <p>: <span>Rp. 3.050.000 (COD)</span></p>
                          </div>
                        </div>
                      </div>
                      <div class="column is-2">
                        <div
                          class="container has-text-centered box has-background-warning has-text-light"
                        >
                          <p>Belum</p>
                        </div>
                      </div>
                    </div>
                    <div class="columns is-vcentered box">
                      <div class="column">
                        <div class="columns container">
                          <div class="column is-2 px-0">
                            <figure class="image">
                              <img :src="item.image" alt="" />
                            </figure>
                          </div>
                          <div class="column">
                            <p class="is-size-6 has-text-weight-medium">
                              {{ item.title }}
                            </p>
                          </div>
                        </div>
                        <div class="columns container is-size-7">
                          <div class="column is-3">
                            <p>Alamat</p>
                            <p>Tanggal Pelaksanaan</p>
                            <p>Tanggal Order</p>
                            <p>Paket</p>
                            <p>Biaya</p>
                          </div>
                          <div class="column">
                            <p>
                              :
                              <span
                                >Perum Doko Indah Blok C18 Kota Kediri Jawa
                                Timur</span
                              >
                            </p>
                            <p>
                              : <span>11-09-2020 s/d 12-09-2020 (2 hari)</span>
                            </p>
                            <p>: <span>09-09-2020</span></p>
                            <p>: <span>Premium</span></p>
                            <p>: <span>Rp. 3.050.000 (COD)</span></p>
                          </div>
                        </div>
                      </div>
                      <div class="column is-2">
                        <div
                          class="container has-text-centered box has-background-success has-text-light"
                        >
                          <p>Selesai</p>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
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
      expandOnHover: false,
      mobile: 'reduce',
      reduce: false,
      rating: {
        bars: true,
        rate: 4.9,
        maxs: 5,
        sizes: 'is-small',
        packs: 'mdi',
        icons: 'star',
        score: true,
        custom: '',
        isRtl: false,
        isSpaced: false,
        isDisabled: true,
        locale: undefined, // Browser locale
      },
      items: [
        {
          title:
            'Some reason why my mouth have been silence in one of stopmoment',
          image:
            'https://cdna.artstation.com/p/assets/images/images/010/098/130/large/sajal-kr-chand-flat-landscape.jpg?1522574693',
          rating: 4.4,
        },
      ],
      isSwitchedCustom: 'Aktif',
    }
  },
}
</script>

<style>
.has-text-halo {
  color: #f79351;
}
.has-background-halo {
  background-color: #f79351;
}
.button.is-halo {
  background-color: #f79351;
  border-color: transparent;
  color: #fff;
  border-radius: 10px;
}
.navbar-start {
  width: 80%;
}
.field.py-2 {
  width: 80%;
}
.HEADER {
  border-bottom-style: ridge;
  border-color: hsl(0, 0%, 86%);
  border-width: thin;
}
.navbar-start input {
  border-radius: 8px;
  border-color: darkgray;
}
.ROOT {
  margin: 0rem 6rem;
}
.PHOTO-PROFILE {
  width: 10rem;
  height: 10rem;
  border-color: #f79351;
  border-width: thin;
  border-style: solid;
  border-radius: 290486px;
}
.DOT-STATUS {
  width: 15px;
  height: 15px;
  background-color: greenyellow;
  border-radius: 290486px;
  position: absolute;
  bottom: 16px;
  right: 16px;
}
.p-1 {
  padding: 1em;
}
.sidebar-page {
  display: flex;
  flex-direction: column;
  width: 100%;
  min-height: 100%;
}
.sidebar-layout {
  display: flex;
  flex-direction: row;
  min-height: 100%;
}
</style>
