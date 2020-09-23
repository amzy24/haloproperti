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
            <div class="container pr-1 has-text-centered">
              <button
                class="PHOTO-PROFILE button is-rounded container"
                @click="isEditPhotoModal = true"
              >
                <img
                  src="https://raw.githubusercontent.com/AmzyZy24/Item/master/no-icon.png"
                  alt=""
                  width="100%"
                />
                <div class="DOT-STATUS container"></div>
              </button>
              <b-modal
                v-model="isEditPhotoModal"
                has-modal-card
                trap-focus
                :destroy-on-hide="false"
                aria-role="dialog"
                aria-modal
              >
                <template #default="props">
                  <modal-form v-bind="formProps" @close="props.close">
                    <div class="modal-card" style="width: auto;">
                      <header class="modal-card-head">
                        <p class="modal-card-title mr-6">
                          Perbarui Foto Profil
                        </p>
                        <button
                          type="button"
                          class="delete"
                          @click="$emit('close')"
                        />
                      </header>
                      <section class="modal-card-body">
                        <div class="PHOTO-PROFILE container">
                          <img
                            src="https://raw.githubusercontent.com/AmzyZy24/Item/master/no-icon.png"
                            alt=""
                            width="100%"
                          />
                          <div class="DOT-STATUS container"></div>
                        </div>
                        <div class="container">
                          <p class="is-size-7 my-4">maksimal ukuran 2 mb</p>
                          <button class="button is-halo is-small">
                            + Unggah
                          </button>
                        </div>
                      </section>
                      <footer class="modal-card-foot">
                        <div class="container">
                          <button class="button is-halo">Batal</button>
                          <button class="button is-halo">Simpan</button>
                        </div>
                      </footer>
                    </div>
                  </modal-form>
                </template>
              </b-modal>
            </div>
          </div>
          <div class="column columns mx-5 has-text-weight-semibold">
            <div class="column has-text-weight-medium">
              <div class="container my-4 is-size-6">Ramzy123</div>
              <div class="container my-4 is-size-6">Kediri</div>
              <div class="container my-4 is-size-6">Bergabung Tahun 2020</div>
            </div>
            <div class="column has-text-weight-medium">
              <div class="container my-4 is-size-6">Mitra Level 1</div>
              <div class="container my-4 is-size-6">10 Total Pesanan</div>
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
                    <b-menu class="is-custom-mobile is-size-6">
                      <b-menu-list label="Akun Personal">
                        <b-menu-item active label="Profile"> </b-menu-item>
                        <b-menu-item label="Password"></b-menu-item>
                        <b-menu-item label="Pesanan Saya"></b-menu-item>
                      </b-menu-list>
                      <b-menu-list label="Mitra" disabled>
                        <b-menu-item label="Jasa" disabled></b-menu-item>
                        <b-menu-item label="Orderan" disabled></b-menu-item>
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
              <div class="container my-5 is-size-5">Profile</div>
              <div class="PROFILE container mx-5 px-5">
                <b-field label="Name" class="mb-5">
                  <b-input value="Mohammad Ammar Ramzy"></b-input>
                </b-field>

                <b-field label="Email">
                  <b-input
                    type="email"
                    value="amzyzy24@gmail.com"
                    maxlength="30"
                  >
                  </b-input>
                </b-field>

                <b-field label="Username">
                  <b-input value="Ramzy123" maxlength="30"></b-input>
                </b-field>

                <b-field label="Jenis Kelamin" class="mb-5">
                  <div class="control">
                    <label class="radio">
                      <input type="radio" name="foobar" />
                      Laki-laki
                    </label>
                    <label class="radio">
                      <input type="radio" name="foobar" />
                      Perempuan
                    </label>
                    <label class="radio">
                      <input type="radio" name="foobar" checked />
                      Lain-lain
                    </label>
                  </div>
                </b-field>

                <b-field label="Tanggal Lahir" class="mb-5">
                  <div class="columns">
                    <div class="column">
                      <b-select placeholder="Pilih Tahun" expanded>
                        <option>2020</option>
                        <option>2019</option>
                        <option>2018</option>
                        <option>2017</option>
                        <option>2016</option>
                        <option>2015</option>
                        <option>2014</option>
                        <option>2013</option>
                        <option>2012</option>
                        <option>2011</option>
                        <option>2010</option>
                        <option>2009</option>
                        <option>2008</option>
                        <option>2007</option>
                        <option>2006</option>
                        <option>2005</option>
                        <option>2004</option>
                        <option>2003</option>
                        <option>2002</option>
                        <option>2001</option>
                        <option>2000</option>
                        <option>1999</option>
                        <option>1998</option>
                        <option>1997</option>
                        <option>1996</option>
                        <option>1995</option>
                        <option>1994</option>
                        <option>1993</option>
                        <option>1992</option>
                        <option>1991</option>
                        <option>1990</option>
                      </b-select>
                    </div>
                    <div class="column">
                      <b-select placeholder="Pilih Bulan" expanded>
                        <option>Januari</option>
                        <option>Februari</option>
                        <option>Maret</option>
                        <option>April</option>
                        <option>Mei</option>
                        <option>Juni</option>
                        <option>Juli</option>
                        <option>Agustus</option>
                        <option>September</option>
                        <option>Oktober</option>
                        <option>November</option>
                        <option>Desember</option>
                      </b-select>
                    </div>
                    <div class="column">
                      <b-select placeholder="Pilih Tanggal" expanded>
                        <option>01</option>
                        <option>02</option>
                        <option>03</option>
                        <option>04</option>
                        <option>05</option>
                        <option>06</option>
                        <option>07</option>
                        <option>08</option>
                        <option>09</option>
                        <option>10</option>
                        <option>11</option>
                        <option>12</option>
                        <option>13</option>
                        <option>14</option>
                        <option>15</option>
                        <option>16</option>
                        <option>17</option>
                        <option>18</option>
                        <option>19</option>
                        <option>20</option>
                        <option>21</option>
                        <option>22</option>
                        <option>23</option>
                        <option>24</option>
                        <option>25</option>
                        <option>26</option>
                        <option>27</option>
                        <option>28</option>
                        <option>29</option>
                        <option>30</option>
                        <option>31</option>
                      </b-select>
                    </div>
                  </div>
                </b-field>

                <b-field label="Telepon" class="mb-5">
                  <b-input value="085730849169"></b-input>
                </b-field>

                <div class="columns">
                  <div class="column is-third">
                    <b-field label="Provinsi">
                      <b-select expanded>
                        <option>Jawa Timur</option>
                        <option>Jawa Barat</option>
                        <option>Jawa Tengah</option>
                        <option>Sulawesi</option>
                        <option>Kalimantan</option>
                        <option>Papua</option>
                        <option>Bali</option>
                      </b-select>
                    </b-field>
                  </div>
                  <div class="column is-third">
                    <b-field label="Kota">
                      <b-select expanded>
                        <option>Surabaya</option>
                        <option>Malang</option>
                        <option>Kediri</option>
                        <option>Blitar</option>
                      </b-select>
                    </b-field>
                  </div>
                  <div class="column is-third">
                    <b-field label="Kodepos">
                      <b-input value="64122"></b-input>
                    </b-field>
                  </div>
                </div>

                <b-field label="Alamat" class="mb-5">
                  <b-input
                    maxlength="200"
                    type="textarea"
                    rows="1"
                    value="Jl. Masjid Al-Huda no.88 Ngadirejo"
                  >
                  </b-input>
                </b-field>
              </div>
              <div class="container has-text-centered">
                <a class="button is-halo is-small">
                  Simpan
                </a>
              </div>
            </div>
            <div class="container">
              <div class="container my-5 is-size-5">Password</div>
              <div class="container has-text-right">
                <div class="container is-size-7 mr-6">
                  <a class="has-text-halo" href="">Lupa password?</a>
                </div>
              </div>
              <div class="PASSWORD container mx-5 px-5 mb-6">
                <b-field label="Password Lama">
                  <b-input
                    type="password"
                    placeholder="Isi dengan password lama"
                    password-reveal
                  >
                  </b-input>
                </b-field>
                <b-field label="Password Baru">
                  <b-input
                    type="password"
                    placeholder="Isi dengan password baru"
                    password-reveal
                  >
                  </b-input>
                </b-field>
                <b-field label="Konfirmasi Password Baru">
                  <b-input
                    type="password"
                    placeholder="Isi dengan password baru"
                    password-reveal
                  >
                  </b-input>
                </b-field>
              </div>
              <div class="container has-text-centered">
                <a class="button is-halo is-small">
                  Simpan
                </a>
              </div>
            </div>
            <div class="container">
              <div class="container my-5 is-size-5">Pesanan Saya</div>
              <b-tabs type="is-boxed" expanded>
                <b-tab-item label="Semua">
                  <div class="card-pp" v-for="(item, i) in items" :key="i">
                    <div class="container box">
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Tanggal Pesanan</p>
                          <p>14 September 2020</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Nomor Pesanan</p>
                          <p>2020091410390003</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Status</p>
                          <p class="has-text-warning">Proses</p>
                        </div>
                        <b-button
                          class="button is-small is-size-7 is-halo"
                          @click="isComponentModalActive = true"
                        >
                          <p>Detail</p>
                        </b-button>
                        <b-modal
                          v-model="isComponentModalActive"
                          has-modal-card
                          trap-focus
                          :destroy-on-hide="false"
                          aria-role="dialog"
                          aria-modal
                        >
                          <template #default="props">
                            <modal-form v-bind="formProps" @close="props.close">
                              <div class="modal-card" style="width: auto;">
                                <header class="modal-card-head">
                                  <p class="modal-card-title">Detail Pesanan</p>
                                  <button
                                    type="button"
                                    class="delete"
                                    @click="$emit('close')"
                                  />
                                </header>
                                <section class="modal-card-body">
                                  <div class="REQUEST container mx-2 my-2">
                                    <div class="BORDER-BOTTOM container mb-3">
                                      <div class="container mb-3">
                                        <p class="has-text-grey-light">
                                          Tanggal Pesanan
                                        </p>
                                        <p class="is-size-6">
                                          14 September 2020
                                        </p>
                                      </div>
                                      <div class="container mb-3">
                                        <p class="has-text-grey-light">
                                          Nomor Pesanan
                                        </p>
                                        <p class="is-size-6">
                                          2020091410390003
                                        </p>
                                      </div>
                                      <div class="container mb-3">
                                        <p class="has-text-grey-light">
                                          Status
                                        </p>
                                        <p class="has-text-warning is-size-6">
                                          Proses
                                        </p>
                                      </div>
                                    </div>
                                    <div class="BORDER-BOTTOM container mb-3">
                                      <div class="container is-2 mb-3">
                                        <p class="has-text-grey-light">Mitra</p>
                                        <p class="is-size-6">
                                          Jokowi
                                        </p>
                                      </div>
                                      <div class="columns">
                                        <div class="column">
                                          <p class="has-text-grey-light">
                                            Jasa
                                          </p>
                                          <div class="container columns">
                                            <div class="column is-3">
                                              <figure class="image">
                                                <img :src="item.image" alt="" />
                                              </figure>
                                            </div>
                                            <div class="column">
                                              <p
                                                class="is-size-6 has-text-weight-medium"
                                              >
                                                {{ item.title }}
                                              </p>
                                            </div>
                                          </div>
                                        </div>
                                        <div class="column is-4">
                                          <p class="has-text-grey-light">
                                            Jumlah
                                          </p>
                                          <p class="is-size-6">2 (Hari)</p>
                                        </div>
                                      </div>
                                      <div class="container is-2 mb-3">
                                        <p class="has-text-grey-light">Paket</p>
                                        <div>
                                          <p class="is-size-6">
                                            Premium
                                          </p>
                                          <div
                                            class="container is-size-7 has-text-grey has-text-weight-medium"
                                          >
                                            <ul
                                              class="LIST columns is-multiline"
                                            >
                                              <li
                                                class="column is-one-quarter py-5"
                                              >
                                                <b-icon
                                                  icon="check"
                                                  type="is-success"
                                                  size="is-small"
                                                ></b-icon>
                                                <span>Fasilitas 1</span>
                                              </li>
                                              <li
                                                class="column is-one-quarter py-5"
                                              >
                                                <b-icon
                                                  icon="check"
                                                  type="is-success"
                                                  size="is-small"
                                                ></b-icon>
                                                <span>Fasilitas 2</span>
                                              </li>
                                              <li
                                                class="column is-one-quarter py-5"
                                              >
                                                <b-icon
                                                  icon="check"
                                                  type="is-success"
                                                  size="is-small"
                                                ></b-icon>
                                                <span>Fasilitas 3</span>
                                              </li>
                                              <li
                                                class="column is-one-quarter py-5"
                                              >
                                                <b-icon
                                                  icon="check"
                                                  type="is-success"
                                                  size="is-small"
                                                ></b-icon>
                                                <span>Fasilitas 4</span>
                                              </li>
                                              <li
                                                class="column is-one-quarter py-5"
                                              >
                                                <b-icon
                                                  icon="check"
                                                  type="is-success"
                                                  size="is-small"
                                                ></b-icon>
                                                <span>Fasilitas 5</span>
                                              </li>
                                              <li
                                                class="column is-one-quarter py-5"
                                              >
                                                <b-icon
                                                  icon="check"
                                                  type="is-success"
                                                  size="is-small"
                                                ></b-icon>
                                                <span>Fasilitas 6</span>
                                              </li>
                                              <li
                                                class="column is-one-quarter py-5"
                                              >
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
                                      <div class="container mb-3">
                                        <p class="has-text-grey-light">
                                          Biaya
                                        </p>
                                        <p class="is-size-6">Rp. 3.000.000</p>
                                      </div>
                                    </div>
                                    <div class="BORDER-BOTTOM container mb-3">
                                      <div class="container mb-3">
                                        <p class="has-text-grey-light">
                                          Client
                                        </p>
                                        <div class="columns is-size-6">
                                          <div class="column is-4">
                                            <p>Nama</p>
                                            <p>Telepon</p>
                                            <p>Alamat</p>
                                            <p>Kota</p>
                                            <p>Provinsi</p>
                                            <p>Kodepos</p>
                                          </div>
                                          <div class="column">
                                            <p>
                                              :
                                              <span>Mohammad Ammar Ramzy</span>
                                            </p>
                                            <p>: <span>085730849169</span></p>
                                            <p>
                                              :
                                              <span
                                                >Jl. Masjid Al-Huda No. 88
                                                Ngadirejo</span
                                              >
                                            </p>
                                            <p>: <span>Kota Kediri</span></p>
                                            <p>: <span>Jawa Timur</span></p>
                                            <p>: <span>64122</span></p>
                                          </div>
                                        </div>
                                      </div>
                                    </div>
                                    <div class="container">
                                      <p class="has-text-grey-light">
                                        Pembayaran
                                      </p>
                                      <div class="columns is-size-6">
                                        <div class="column is-4">
                                          <p>Total Harga Jasa</p>
                                          <p>Biaya Layanan</p>
                                          <p>Charge</p>
                                          <p>Total Bayar</p>
                                          <p>Metode Pembayaran</p>
                                        </div>
                                        <div class="column">
                                          <p>
                                            :
                                            <span>Rp. 3.000.000</span>
                                          </p>
                                          <p>: <span>Rp. 50.000</span></p>
                                          <p>
                                            :
                                            <span>Rp. 0</span>
                                          </p>
                                          <p>: <span>Rp. 3.050.000</span></p>
                                          <p>: <span>Bank BCA</span></p>
                                        </div>
                                      </div>
                                    </div>
                                  </div>
                                </section>
                                <footer class="modal-card-foot"></footer>
                              </div>
                            </modal-form>
                          </template>
                        </b-modal>
                      </div>
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Jasa</p>
                          <div class="container columns">
                            <div class="column is-3">
                              <figure class="image">
                                <img :src="item.image" alt="" />
                              </figure>
                            </div>
                            <div class="column">
                              <p class="is-size-7 has-text-weight-medium">
                                {{ item.title }}
                              </p>
                            </div>
                          </div>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Mitra</p>
                          <p class="has-text-weight-semibold">
                            Jokowi
                          </p>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Paket</p>
                          <p class="has-text-weight-semibold">
                            Premium
                          </p>
                        </div>
                        <div class="column is-2 has-text-right">
                          <p class="has-text-grey-light">Biaya</p>
                          <p>Rp. 3.000.000</p>
                        </div>
                      </div>
                    </div>

                    <div class="container box">
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Tanggal Pesanan</p>
                          <p>12 September 2020</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Nomor Pesanan</p>
                          <p>2020091210390002</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Status</p>
                          <p class="has-text-danger">Dibatalkan</p>
                        </div>
                        <b-button class="button is-small is-size-7 is-halo">
                          <p>Detail</p>
                        </b-button>
                      </div>
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Jasa</p>
                          <div class="container columns">
                            <div class="column is-3">
                              <figure class="image">
                                <img :src="item.image" alt="" />
                              </figure>
                            </div>
                            <div class="column">
                              <p class="is-size-7 has-text-weight-medium">
                                {{ item.title }}
                              </p>
                            </div>
                          </div>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Mitra</p>
                          <p class="has-text-weight-semibold">
                            Jokowi
                          </p>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Paket</p>
                          <p class="has-text-weight-semibold">
                            Premium
                          </p>
                        </div>
                        <div class="column is-2 has-text-right">
                          <p class="has-text-grey-light">Biaya</p>
                          <p>Rp. 3.000.000</p>
                        </div>
                      </div>
                    </div>

                    <div class="container box">
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Tanggal Pesanan</p>
                          <p>11 September 2020</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Nomor Pesanan</p>
                          <p>2020091110390001</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Status</p>
                          <p class="has-text-success">Selesai</p>
                        </div>
                        <b-button class="button is-small is-size-7 is-halo">
                          <p>Detail</p>
                        </b-button>
                      </div>
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Jasa</p>
                          <div class="container columns">
                            <div class="column is-3">
                              <figure class="image">
                                <img :src="item.image" alt="" />
                              </figure>
                            </div>
                            <div class="column">
                              <p class="is-size-7 has-text-weight-medium">
                                {{ item.title }}
                              </p>
                            </div>
                          </div>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Mitra</p>
                          <p class="has-text-weight-semibold">
                            Jokowi
                          </p>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Paket</p>
                          <p class="has-text-weight-semibold">
                            Premium
                          </p>
                        </div>
                        <div class="column is-2 has-text-right">
                          <p class="has-text-grey-light">Biaya</p>
                          <p>Rp. 3.000.000</p>
                        </div>
                      </div>
                    </div>
                  </div>
                </b-tab-item>
                <b-tab-item label="Proses">
                  <div class="card-pp" v-for="(item, i) in items" :key="i">
                    <div class="container box">
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Tanggal Pesanan</p>
                          <p>14 September 2020</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Nomor Pesanan</p>
                          <p>2020091410390003</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Status</p>
                          <p class="has-text-warning">Proses</p>
                        </div>
                        <b-button class="button is-small is-size-7 is-halo">
                          <p>Detail</p>
                        </b-button>
                      </div>
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Jasa</p>
                          <div class="container columns">
                            <div class="column is-3">
                              <figure class="image">
                                <img :src="item.image" alt="" />
                              </figure>
                            </div>
                            <div class="column">
                              <p class="is-size-7 has-text-weight-medium">
                                {{ item.title }}
                              </p>
                            </div>
                          </div>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Mitra</p>
                          <p class="has-text-weight-semibold">
                            Jokowi
                          </p>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Paket</p>
                          <p class="has-text-weight-semibold">
                            Premium
                          </p>
                        </div>
                        <div class="column is-2 has-text-right">
                          <p class="has-text-grey-light">Biaya</p>
                          <p>Rp. 3.000.000</p>
                        </div>
                      </div>
                    </div>
                  </div>
                </b-tab-item>
                <b-tab-item label="Selesai">
                  <div class="card-pp" v-for="(item, i) in items" :key="i">
                    <div class="container box">
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Tanggal Pesanan</p>
                          <p>11 September 2020</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Nomor Pesanan</p>
                          <p>2020091110390001</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Status</p>
                          <p class="has-text-success">Selesai</p>
                        </div>
                        <b-button class="button is-small is-size-7 is-halo">
                          <p>Detail</p>
                        </b-button>
                      </div>
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Jasa</p>
                          <div class="container columns">
                            <div class="column is-3">
                              <figure class="image">
                                <img :src="item.image" alt="" />
                              </figure>
                            </div>
                            <div class="column">
                              <p class="is-size-7 has-text-weight-medium">
                                {{ item.title }}
                              </p>
                            </div>
                          </div>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Mitra</p>
                          <p class="has-text-weight-semibold">
                            Jokowi
                          </p>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Paket</p>
                          <p class="has-text-weight-semibold">
                            Premium
                          </p>
                        </div>
                        <div class="column is-2 has-text-right">
                          <p class="has-text-grey-light">Biaya</p>
                          <p>Rp. 3.000.000</p>
                        </div>
                      </div>
                    </div>
                  </div>
                </b-tab-item>
                <b-tab-item label="Dibatalkan">
                  <div class="card-pp" v-for="(item, i) in items" :key="i">
                    <div class="container box">
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Tanggal Pesanan</p>
                          <p>12 September 2020</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Nomor Pesanan</p>
                          <p>2020091210390002</p>
                        </div>
                        <div class="column has-text-centered">
                          <p class="has-text-grey-light">Status</p>
                          <p class="has-text-danger">Dibatalkan</p>
                        </div>
                        <b-button class="button is-small is-size-7 is-halo">
                          <p>Detail</p>
                        </b-button>
                      </div>
                      <div class="columns is-vcentered is-size-7">
                        <div class="column">
                          <p class="has-text-grey-light">Jasa</p>
                          <div class="container columns">
                            <div class="column is-3">
                              <figure class="image">
                                <img :src="item.image" alt="" />
                              </figure>
                            </div>
                            <div class="column">
                              <p class="is-size-7 has-text-weight-medium">
                                {{ item.title }}
                              </p>
                            </div>
                          </div>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Mitra</p>
                          <p class="has-text-weight-semibold">
                            Jokowi
                          </p>
                        </div>
                        <div class="column is-2 has-text-centered">
                          <p class="has-text-grey-light">Paket</p>
                          <p class="has-text-weight-semibold">
                            Premium
                          </p>
                        </div>
                        <div class="column is-2 has-text-right">
                          <p class="has-text-grey-light">Biaya</p>
                          <p>Rp. 3.000.000</p>
                        </div>
                      </div>
                    </div>
                  </div>
                </b-tab-item>
              </b-tabs>
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
      isEditPhotoModal: false,
      isComponentModalActive: false,
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
    }
  },
}
</script>

<style>
.has-text-halo {
  color: #f79351;
}
.is-halo {
  background: #f79351;
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
.REQUEST {
  max-height: 450px;
  width: 600px;
}
.BORDER-BOTTOM {
  border-bottom-style: solid;
  border-color: hsl(0, 0%, 86%);
  border-width: thin;
}
</style>
