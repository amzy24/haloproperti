<template>
  <section>
    <section class="ROOT section px-0 py-0">
      <section class="HEADER section py-5 px-3 mx-6">
        <nav class="navbar" role="navigation" aria-label="main navigation">
          <div class="navbar-brand">
            <a class="navbar-item" href="/">
              <img src="~/assets/2.png" width="150" />
            </a>

            <a
              role="button"
              v-bind:class="['navbar-burger burger', { 'is-active': isActive }]"
              aria-label="menu"
              aria-expanded="false"
              data-target="navbarBasicExample"
              @click="isActive = !isActive"
            >
              <span aria-hidden="true"></span>
              <span aria-hidden="true"></span>
              <span aria-hidden="true"></span>
            </a>
          </div>

          <div
            id="navbarBasicExample"
            v-bind:class="['navbar-menu', { 'is-active': isActive }]"
          >
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
                  <button
                    class="button is-light mx-3"
                    @click="isCard2ModalActive = true"
                  >
                    <strong>
                      Gabung Mitra
                    </strong>
                  </button>
                  <button
                    class="button is-halo mx-3"
                    @click="isCardModalActive = true"
                  >
                    <strong>
                      Masuk
                    </strong>
                  </button>
                  <b-dropdown
                    v-model="navigation"
                    position="is-bottom-left"
                    append-to-body
                    aria-role="menu"
                  >
                    <a class="navbar-item pt-0" slot="trigger" role="button">
                      <img
                        src="~assets/045-facebook.png"
                        alt=""
                        class="foto is-rounded"
                      />
                    </a>

                    <b-dropdown-item custom aria-role="menuitem">
                      Logged as <b>Rafael Beraldo</b>
                    </b-dropdown-item>
                    <hr class="dropdown-divider" />
                    <b-dropdown-item has-link aria-role="menuitem">
                      <a href="https://google.com" target="_blank">
                        <b-icon icon="link"></b-icon>
                        Google (link)
                      </a>
                    </b-dropdown-item>
                    <b-dropdown-item value="home" aria-role="menuitem">
                      <b-icon icon="home"></b-icon>
                      Home
                    </b-dropdown-item>
                    <b-dropdown-item value="products" aria-role="menuitem">
                      <b-icon icon="cart"></b-icon>
                      Products
                    </b-dropdown-item>
                    <b-dropdown-item value="blog" disabled aria-role="menuitem">
                      <b-icon icon="book-open"></b-icon>
                      Blog
                    </b-dropdown-item>
                    <hr class="dropdown-divider" aria-role="menuitem" />
                    <b-dropdown-item value="settings">
                      <b-icon icon="settings"></b-icon>
                      Settings
                    </b-dropdown-item>
                    <b-dropdown-item value="logout" aria-role="menuitem">
                      <b-icon icon="logout"></b-icon>
                      Logout
                    </b-dropdown-item>
                  </b-dropdown>
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
        </nav>
      </section>
      <section class="MAIN">
        <nuxt />
      </section>
    </section>
    <!-- ------------------------------------- -->
    <footer class="FOOTER has-background-halo">
      <div class="FOOTER-CONTENT container columns is-fullhd mx-6 my-0">
        <div class="F-FIRST column is-one-third has-text-centered mt-5 pt-5">
          <div class="title is-4 has-text-weight-bold">Halo Properti</div>
          <div class="ICON-SOSMED container">
            <div class="block">
              <a href="#">
                <span class="icon mx-2">
                  <b-icon icon="facebook" custom-size="mdi-24px"> </b-icon
                ></span>
              </a>
              <a href="#">
                <span class="icon mx-2">
                  <b-icon icon="twitter" custom-size="mdi-24px"> </b-icon
                ></span>
              </a>
              <a href="#">
                <span class="icon mx-2">
                  <b-icon icon="instagram" custom-size="mdi-24px"> </b-icon
                ></span>
              </a>
              <a href="#">
                <span class="icon mx-2">
                  <b-icon icon="youtube" custom-size="mdi-24px"> </b-icon
                ></span>
              </a>
            </div>
          </div>
        </div>
        <div
          class="SECOND column mt-5 is-one-third pl-5 mb-5 has-text-weight-bold"
        >
          <div class="columns is-mobile">
            <div class="column is-half">
              <a href="/tentang" class="has-text-dark">Tentang Kami</a><br />
              <a href="/tentang" class="has-text-dark">Layanan Kami</a><br />
              <a href="/tentang" class="has-text-dark">Mitra Kami</a>
            </div>
            <div class="column is-half">
              <a href="/tentang" class="has-text-dark">Kontak Kami</a><br />
              <a href="/tentang" class="has-text-dark">Pusat Bantuan</a><br />
              <a href="/tentang" class="has-text-dark">Kebijakan Privasi</a>
            </div>
          </div>
        </div>
        <div class="THIRD column mt-5 is-one-third has-text-weight-bold">
          <div class="container has-text-dark">Unduh Aplikasi</div>
          <div class="LINK-APP container mx-2 my-2">
            <div class="APP columns is-mobile">
              <a href=""
                ><figure class="image mx-1 my-2">
                  <img
                    src="https://github.com/amzy24/Item/blob/master/appstore.png?raw=true"
                    src-fallback="https://github.com/amzy24/Item/blob/master/appstore.png?raw=true"
                  /></figure
              ></a>
              <a href=""
                ><figure class="image mx-1 my-2">
                  <img
                    src="https://github.com/amzy24/Item/blob/master/playstore.png?raw=true"
                    src-fallback="https://github.com/amzy24/Item/blob/master/playstore.png?raw=true"
                  /></figure
              ></a>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </section>
</template>

<script>
export default {}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Archivo&family=Teko:wght@300&display=swap');
html,
body {
  font-family: 'Archivo', sans-serif !important;
}
.ROOT {
  margin: 0rem 6rem;
}
.button.is-halo {
  background-color: #f79351;
  border-color: transparent;
  color: #fff;
  border-radius: 10px;
}
.has-text-halo {
  color: #f79351 !important;
}
.has-background-halo {
  background-color: #f79351;
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
.FOOTER {
  height: fit-content;
}
.F-FIRST {
  height: fit-content;
}
.SECOND {
  line-height: 3rem;
}
.THIRD {
  line-height: 3rem;
  height: fit-content;
}
.ICON-SOSMED a {
  color: unset;
}
.APP {
  margin-right: 8rem;
}
.APP figure img {
  border-radius: 2px;
}
img.foto.is-rounded {
  border-radius: 62%;
  width: 31pt;
  max-height: 100%;
}
/* -------------RESPONSIVE--------------- */
@media screen and (max-width: 768px) {
  .FOOTER-CONTENT {
    margin-left: 0rem !important;
    margin-right: 0rem !important;
    text-align: center;
  }
  .SECOND {
    margin-top: 1rem !important;
    padding-left: 0.75rem !important;
  }
  .ICON-SOSMED {
    justify-content: center;
  }
  .THIRD {
    margin-top: 0rem !important;
  }
  .APP {
    margin-left: 1rem;
    margin-right: 1rem;
  }
  .HEADER {
    margin: 0rem !important;
  }
  .ROOT {
    margin: 0.25rem 0.25rem !important;
  }
  .MAIN-TOP {
    margin-left: 0.25rem !important;
    margin-right: 0.25rem !important;
  }
  .MAIN-BOTTOM {
    margin-left: 0.25rem !important;
    margin-right: 0.25rem !important;
  }
}
</style>
