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
        </div>
      </nav>
    </section>

    <section class="BODY section py-5 px-3 mx-6">
      <div class="container">
        <b-field class="title has-text-centered">
          <p><strong>PENDAFTARAN MITRA</strong></p>
        </b-field>

        <b-field placeholder="shit" label="Nama Mitra">
          <b-input v-model="value"></b-input>
        </b-field>

        <b-field label="Email">
          <b-input v-model="email"> </b-input>
        </b-field>

        <b-field label="No Telp">
          <b-input v-model="value"></b-input>
        </b-field>

        <b-field label="Jenis Jasa" grouped>
          <b-radio v-model="radio" native-value="default">
            Perbaikan/Instalasi
          </b-radio>
          <b-radio v-model="radio" native-value="default">
            Renovasi/Pebangunan
          </b-radio>
          <b-radio v-model="radio" native-value="default">
            Desain
          </b-radio>
          <b-select placeholder="Pilih Jasa" expanded>
            <option value="jenis">Reparasi AC</option>
            <option value="jenis">Reparasi Hitter</option>
          </b-select>
        </b-field>

        <b-field label="Area Cakupan" grouped>
          <b-select placeholder="Area Cakupan">
            <option value="kota">Kediri</option>
            <option value="kota">Malang</option>
            <option value="kota">Surabaya</option>
          </b-select>
          <span></span>
          <b-input expanded>
            <b-tag></b-tag>
          </b-input>
        </b-field>

        <b-field label="Alamat Penggung Jawab">
          <div class="columns is-mobile">
            <div class="column is-2">
              <b-select placeholder="Negara" expanded>
                <option value="negara">Indonesia</option>
              </b-select>
            </div>
            <div class="column is-2">
              <b-select placeholder="Provinsi" expanded>
                <option value="Provinsi">Jawa Timur</option>
              </b-select>
            </div>
            <div class="column is-2">
              <b-select placeholder="Kabupaten/Kota" expanded>
                <option value="Kabupaten/Kota">Kediri</option>
              </b-select>
            </div>
            <div class="column">
              <b-input expanded>
                <option value="Keterangan"></option>
              </b-input>
            </div>
          </div>
        </b-field>

        <b-field label="Deskripsi Mitra">
          <b-input maxlength="200" type="textarea"></b-input>
        </b-field>

        <b-field label="Upload KTP" group>
          <b-upload v-model="dropFiles" multiple drag-drop expanded>
            <section class="section">
              <div class="content has-text-centered">
                <p>
                  <b-icon icon="upload" size="is-large"> </b-icon>
                </p>
                <p>Drop your files here or click to upload</p>
              </div>
            </section>
          </b-upload>
        </b-field>

        <div class="tags">
          <span
            v-for="(file, index) in dropFiles"
            :key="index"
            class="tag is-primary"
          >
            {{ file.name }}
            <button
              class="delete is-small"
              type="button"
              @click="deleteDropFile(index)"
            ></button>
          </span>
        </div>

        <div class="btn has-text-right">
          <b-button position="right">DAFTAR</b-button>
        </div>
      </div>
    </section>
  </section>
</template>
<script></script>
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
li {
  border-bottom-style: ridge;
  border-color: hsl(0, 0%, 86%);
  border-width: thin;
  padding-bottom: 0.5rem;
}
img.foto.is-rounded {
  border-radius: 62%;
  width: 31pt;
  max-height: 100%;
}
</style>
