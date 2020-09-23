<template>
  <section class="ROOT section px-0 py-0">
    <section class="HEADER section py-5 px-3 mx-6">
      <nav class="navbar" role="navigation" aria-label="main navigation">
        <div class="navbar-brand">
          <a class="navbar-item" href="/">
            <img src="~/assets/2.png" width="150" />
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
          <div class="navbar-end">
            <div class="navbar-item">
              <div class="buttons py-3">
                <a href="/upload_profile_comm">
                  <button class="button is-light">
                    <strong>
                      Gabung Mitra
                    </strong>
                  </button>
                </a>
                <button
                  class="button is-halo"
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
                  <a class="navbar-item" slot="trigger" role="button">
                    <img
                      src="~assets/045-facebook.png"
                      alt=""
                      class="foto is-rounded"
                    />
                  </a>

                  <div class="columns py-2 px-2">
                    <div class="column">
                      <h1>Saldo</h1>
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
                    </div>
                    <div class="column">
                      <h1>Account</h1>
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
                      <b-dropdown-item value="logout" aria-role="menuitem">
                        <b-icon icon="logout"></b-icon>
                        Logout
                      </b-dropdown-item>
                    </div>
                  </div>
                </b-dropdown>
              </div>

              <b-modal v-model="isCard2ModalActive" :width="640" scroll="keep">
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
                          <p>
                            Belum memiliki akun?
                            <button
                              class="button is-light"
                              @click="isCard2ModalActive = true"
                            >
                              <strong>
                                Gabung Mitra
                              </strong>
                            </button>
                          </p>
                        </footer>
                      </div>
                    </form>
                  </div>
                </div>
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
            </div>
          </div>
        </div>
      </nav>
    </section>

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
              <a href="/kategori" class="has-text-dark">Konsultan</a><br />
              <a href="/kategori" class="has-text-dark">Persewaan</a><br />
              <a href="/kategori" class="has-text-dark">Produsen</a><br />
              <a href="/kategori" class="has-text-dark">Tenaga</a><br />
              <a href="/kategori" class="has-text-dark">Jasa</a><br />
              <a href="/kategori" class="has-text-dark">Toko</a>
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
          <div class="SHOW-MORE buttons py-5">
            <button class="button is-small is-fullwidth has-text-weight-medium">
              Lebih Banyak V
            </button>
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
.ROOT {
  margin: 0rem 6rem;
}
.button.is-halo {
  background-color: #f79351;
  border-color: transparent;
  color: #fff;
  border-radius: 10px;
}
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
  .ROOT {
    margin: 0.25rem 0.25rem !important;
  }
  .HEADER {
    margin: 0rem !important;
  }
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
img.foto.is-rounded {
  border-radius: 62%;
  width: 31pt;
  max-height: 100%;
}
.button.button {
  margin-right: 0.5rem;
}
</style>
