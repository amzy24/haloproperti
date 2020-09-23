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
              <a class="has-text-dark" href="#">
                <span>Pembayaran</span>
              </a>
            </li>
            <li class="is-active">
              <a class="has-text-halo" href="#">
                <span>Selesai</span>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <section>
      <div class="CENTER container mt-4">
        <div class="columns">
          <div class="column title is-6 mb-0">
            Nomor pesanan
          </div>
          <div class="column has-text-right title is-6">
            #AB123456
          </div>
        </div>
        <div class="container my-4 title is-6">
          <div>Biaya yang harus dibayar</div>
          <div class="title is-2 has-text-centered my-2">Rp. 3.050.000</div>
          <div class="columns is-centered my-1 is-vcentered">
            <div class="column is-4 is-size-7">No. Virtual Account</div>
            <div class="column is-size-5">123456789123456</div>
            <div class="column is-4 has-text-right">
              <b-button size="is-small">Salin</b-button>
            </div>
          </div>
        </div>
        <div>
          <div class="columns my-2">
            <div class="column title is-6 mb-0">
              Metode pembayaran
            </div>
            <div class="column has-text-right title is-6">
              Bank BCA
            </div>
          </div>
          <div class="mb-5">
            <div>
              <b-button class="button" size="is-small" expanded>
                <div class="columns">
                  <div class="column is-half has-text-left">
                    Petunjuk Transfer Virtual Account
                  </div>
                  <div class="column is-half has-text-right">
                    <b-icon :icon="active ? 'menu-up' : 'menu-down'"></b-icon>
                  </div>
                </div>
              </b-button>
              <div class="content mx-6 my-2">
                <ol type="1">
                  <li>Pilih Transaksi Lainnya.</li>
                  <li>Pilih Pembayaran > Pembayaran Lainnya.</li>
                  <li>Pilih Virtual Account.</li>
                  <li>
                    Masukkan kode bayar (no. Virtual Account), kemudian pilih
                    Benar.
                  </li>
                  <li>
                    Periksa informasi yang tertera di layar. Pastikan Merchant
                    adalah Shopee, total tagihan sudah benar, dan username Anda
                    {username}. Jika benar, pilih Benar.
                  </li>
                </ol>
              </div>
            </div>
            <div>
              <b-button class="button" size="is-small" expanded>
                <div class="columns">
                  <div class="column is-half has-text-left">
                    Petunjuk Transfer KlikBCA
                  </div>
                  <div class="column is-half has-text-right">
                    <b-icon :icon="active ? 'menu-up' : 'menu-down'"></b-icon>
                  </div>
                </div>
              </b-button>
            </div>
            <div>
              <b-button class="button" size="is-small" expanded>
                <div class="columns">
                  <div class="column is-half has-text-left">
                    Petunjuk Transfer m-BCA
                  </div>
                  <div class="column is-half has-text-right">
                    <b-icon :icon="active ? 'menu-up' : 'menu-down'"></b-icon>
                  </div>
                </div>
              </b-button>
            </div>
          </div>
          <div class="my-4">
            <b-button
              tag="router-link"
              class="KEMBALI button is-size-7 has-text-centered mt-5"
              to="/"
              size="is-medium"
            >
              Kembali ke halaman utama
            </b-button>
          </div>
        </div>
      </div>
    </section>
  </section>
</template>

<script>
export default {}
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
.BREADCRUMB {
  margin: 0 auto;
}
.BREADCRUMB li {
  letter-spacing: 1.5px;
}
.has-text-halo {
  color: #f79351 !important;
}
.CENTER {
  margin: 0 auto;
  width: 50%;
}
.KEMBALI.button {
  border-radius: 0.5rem;
  background-color: #f79351;
  width: 100%;
  color: #fff;
}
</style>
