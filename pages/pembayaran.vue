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

          <div id="navbarBasicExample" class="navbar-menu">
            <div class="navbar-end">
              <div class="navbar-item">
                <div class="buttons">
                  <button
                    class="button is-light"
                    @click="isCard2ModalActive = true"
                  >
                    <strong>
                      Gabung Mitra
                    </strong>
                  </button>
                  <button
                    class="button is-halo"
                    @click="isCardModalActive = true"
                  >
                    <strong>
                      Masuk
                    </strong>
                  </button>
                </div>

                <b-modal
                  v-model="isCard2ModalActive"
                  :width="640"
                  scroll="keep"
                >
                  <div class="card">
                    <div class="card-content">
                      <form action="">
                        <div class="modal-card" style="width: auto;">
                          <header class="modal-card-head">
                            <p class="modal-card-title">Gabung Mitra</p>
                            <button
                              type="button"
                              class="delete"
                              @click="$emit('close')"
                            />
                          </header>
                          <section class="modal-card-body">
                            <b-field label="Username">
                              <b-input
                                type="username"
                                :value="username"
                                placeholder="Your username"
                                required
                              >
                              </b-input>
                            </b-field>

                            <b-field label="Email">
                              <b-input
                                type="email"
                                :value="email"
                                placeholder="Your email"
                                required
                              >
                              </b-input>
                            </b-field>

                            <b-field label="Password">
                              <b-input
                                type="password"
                                :value="password"
                                password-reveal
                                placeholder="Your password"
                                required
                              >
                              </b-input>
                            </b-field>

                            <b-checkbox
                              ><p>
                                Akan mematuhi ketentuan yang berlaku
                              </p></b-checkbox
                            >
                          </section>
                          <footer class="modal-card-foot">
                            <button class="button is-halo">
                              Gabung
                            </button>
                            <p>Telah Memiliki Akun? <a href="#">Masuk</a></p>
                          </footer>
                        </div>
                      </form>
                    </div>
                  </div>
                </b-modal>

                <b-modal v-model="isCardModalActive" :width="640" scroll="keep">
                  <div class="card">
                    <div class="card-content">
                      <form action="">
                        <div class="modal-card" style="width: auto;">
                          <header class="modal-card-head">
                            <p class="modal-card-title">Login</p>
                            <button
                              type="button"
                              class="delete"
                              @click="$emit('close')"
                            />
                          </header>
                          <section class="modal-card-body">
                            <b-field label="Email">
                              <b-input
                                type="email"
                                :value="email"
                                placeholder="Your email"
                                required
                              >
                              </b-input>
                            </b-field>

                            <b-field label="Password">
                              <b-input
                                type="password"
                                :value="password"
                                password-reveal
                                placeholder="Your password"
                                required
                              >
                              </b-input>
                            </b-field>

                            <b-checkbox>Remember me</b-checkbox>

                            <div class="option mt-3 has-text-centered">
                              <div><p>or login with</p></div>
                              <a href="#">
                                <img
                                  src="https://img.icons8.com/color/30/000000/google-logo.png"
                                  alt=""
                                />
                              </a>
                              <a href="#">
                                <img
                                  src="https://img.icons8.com/color/30/000000/facebook-circled.png"
                                  alt=""
                                />
                              </a>
                              <a href="#">
                                <img
                                  src="https://img.icons8.com/material-sharp/30/000000/github.png"
                                />
                              </a>
                              <a href="#">
                                <img
                                  src="https://img.icons8.com/color/30/000000/microsoft.png"
                                />
                              </a>
                            </div>
                          </section>
                          <footer class="modal-card-foot">
                            <button class="button is-halo">
                              Login
                            </button>
                            <p>Belum memiliki akun? <a href="#">Gabung</a></p>
                          </footer>
                        </div>
                      </form>
                    </div>
                  </div>
                </b-modal>
              </div>
            </div>
          </div>
        </div>
      </nav>
    </section>
    <nav class="navbar pt-2 mx-6">
      <div
        class="BREADCRUMB breadcrumb has-succeeds-separator is-small is-size-7 has-text-weight-medium"
        aria-label="breadcrumbs"
      >
        <div>
          <ul>
            <li class="is-active">
              <a class="has-text-dark" href="#">
                <span>Pesanan</span>
              </a>
            </li>
            <li class="is-active">
              <a class="has-text-halo" href="#">
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
    <section class="section px-6 py-4 mb-6">
      <div class="container">
        <div class="columns">
          <div class="DATA-CUSTOMER column is-8 mr-5 mx-4">
            <div class="container mb-5">
              <div class="title is-5 container">Data Customer</div>
              <div class="BORDER columns is-size-6 pb-5">
                <div class="column is-4">
                  <p>
                    Mohammad Ammar Ramzy <br />
                    (+62) 85730849169
                  </p>
                </div>
                <div class="column">
                  <p>
                    Jl. Masjid Al-Huda No.88 Ngadirejo, Kota Kediri, Jawa Timur
                    64122
                  </p>
                </div>
                <div class="column is-1 px-0">
                  <b-button class="BUTTON-EDIT button is-small is-size-6">
                    <p>Edit</p>
                  </b-button>
                </div>
              </div>
            </div>
            <div class="container mb-5">
              <div class="title is-5 container">Metode Pembayaran</div>
              <div class="BORDER columns is-size-6 pb-5 pt-4">
                <b-tabs
                  :position="atRight ? 'is-right' : ''"
                  size="is-medium"
                  type="is-boxed"
                  vertical
                >
                  <b-tab-item label="Cash">
                    Bayar di tempat
                  </b-tab-item>

                  <b-tab-item label="Bank Transfer">
                    <div class="field">
                      <b-radio v-model="radio" native-value="BCA">
                        Bank BCA
                      </b-radio>
                    </div>
                    <div class="field">
                      <b-radio v-model="radio" native-value="BNI">
                        Bank BNI
                      </b-radio>
                    </div>
                    <div class="field">
                      <b-radio v-model="radio" native-value="BRI">
                        Bank BRI
                      </b-radio>
                    </div>
                    <div class="field">
                      <b-radio v-model="radio" native-value="Mandiri">
                        Bank Mandiri
                      </b-radio>
                    </div>
                  </b-tab-item>
                </b-tabs>
              </div>
            </div>
          </div>
          <div class="column">
            <div class="BAYAR-PANEL column px-4">
              <section class="sidebar">
                <div class="card-pp" v-for="(item, i) in items" :key="i">
                  <div class="BORDER-BOTTOM columns is-vcentered pb-4">
                    <div class="column is-3 px-0 pt-1">
                      <figure class="image">
                        <img :src="item.image" alt="" />
                      </figure>
                    </div>
                    <div class="column pr-0 pt-1">
                      <p class="is-size-7 has-text-weight-medium">
                        {{ item.title }}
                      </p>
                    </div>
                  </div>
                  <div>
                    <div class="columns is-vcentered">
                      <div
                        class="column is-size-6 has-text-weight-semibold pb-0"
                      >
                        Paket Premium
                      </div>
                      <div
                        class="column is-size-7 has-text-weight-bold has-text-right pb-0"
                      >
                        Rp. 1.500.000
                      </div>
                    </div>
                    <div
                      class="container is-size-7 has-text-grey has-text-weight-medium"
                    >
                      <ul class="LIST">
                        <li class="py-2">
                          <b-icon
                            icon="check"
                            type="is-success"
                            size="is-small"
                          ></b-icon>
                          <span>Fasilitas 1</span>
                        </li>
                        <li class="py-2">
                          <b-icon
                            icon="check"
                            type="is-success"
                            size="is-small"
                          ></b-icon>
                          <span>Fasilitas 2</span>
                        </li>
                        <li class="py-2">
                          <b-icon
                            icon="check"
                            type="is-success"
                            size="is-small"
                          ></b-icon>
                          <span>Fasilitas 3</span>
                        </li>
                        <li class="py-2">
                          <b-icon
                            icon="check"
                            type="is-success"
                            size="is-small"
                          ></b-icon>
                          <span>Fasilitas 4</span>
                        </li>
                        <li class="py-2">
                          <b-icon
                            icon="check"
                            type="is-success"
                            size="is-small"
                          ></b-icon>
                          <span>Fasilitas 5</span>
                        </li>
                        <li class="py-2">
                          <b-icon
                            icon="check"
                            type="is-success"
                            size="is-small"
                          ></b-icon>
                          <span>Fasilitas 6</span>
                        </li>
                        <li class="py-2">
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
                  <div class="columns pt-2 is-vcentered">
                    <div class="column is-size-6 has-text-weight-semibold pb-0">
                      Jumlah order (Hari)
                    </div>
                    <div
                      class="column is-one-quarter is-size-7 has-text-weight-bold has-text-right pb-0"
                    >
                      2
                    </div>
                  </div>
                  <div class="columns is-vcentered">
                    <div class="column is-size-6 has-text-weight-semibold">
                      Biaya layanan
                    </div>
                    <div
                      class="column is-size-7 has-text-weight-bold has-text-right"
                    >
                      Rp. 50.000
                    </div>
                  </div>
                  <div class="TEXT-TOTAL columns is-vcentered">
                    <div class="column is-3 is-size-6 pl-0">
                      <b>Total</b>
                    </div>
                    <div class="column has-text-right is-size-6 pr-0">
                      <b>Rp. 3.050.000</b>
                    </div>
                  </div>
                  <div class="buttons">
                    <b-button
                      tag="router-link"
                      to="/selesai"
                      type="is-halo"
                      expanded
                      >Bayar</b-button
                    >
                  </div>
                </div>
              </section>
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
      isCard2ModalActive: false,
      isCardModalActive: false,
      activeTab: 'pictures',
      showMusic: true,
      showBooks: false,
      multiline: true,
      items: [
        {
          title: 'I Will Dream Up A Bold High End Logo And Brand',
          image:
            'https://cdna.artstation.com/p/assets/images/images/010/098/130/large/sajal-kr-chand-flat-landscape.jpg?1522574693',
        },
      ],
      radio: 'default',
    }
  },
}
</script>
<style>
.ROOT {
  margin: 0rem 6rem;
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
/* --------------HEADER to MAIN-------------- */
.BREADCRUMB {
  margin: 0 auto;
}
.BREADCRUMB li {
  letter-spacing: 1.5px;
}
.has-text-halo {
  color: #f79351 !important;
}
.BAYAR-PANEL {
  border-style: solid;
  border-width: thin;
  height: fit-content;
  border-color: lightgrey;
  border-radius: 0.25rem;
}
.BORDER-BOTTOM {
  border-bottom-style: solid;
  border-width: thin;
  border-color: lightgrey;
  margin: 0rem 0.2rem;
}
.BUTTON-EDIT {
  border-radius: 0.6rem;
  border-color: none;
  width: 100%;
  border: none;
  color: #f79351;
}
.BORDER {
  border-bottom-style: solid;
  border-width: thin;
  border-color: lightgrey;
  height: fit-content;
}
.TEXT-TOTAL {
  border-top-style: solid;
  border-width: thin;
  border-color: lightgrey;
  margin: 0rem 0.25rem;
}
</style>
