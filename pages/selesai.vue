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
            <b-collapse
              class="card"
              animation="slide"
              v-for="(collapse, index) of collapses"
              :key="index"
              :open="isOpen == index"
              @open="isOpen = index"
            >
              <div
                slot="trigger"
                slot-scope="props"
                class="card-header"
                role="button"
              >
                <p
                  class="card-header-title is-size-7 has-text-grey is-centered has-text-weight-normal"
                >
                  {{ collapse.title }}
                </p>
                <a class="card-header-icon">
                  <b-icon :icon="props.open ? 'menu-up' : 'menu-down'">
                  </b-icon>
                </a>
              </div>
              <div class="card-content">
                <div class="content">
                  {{ collapse.text }}
                </div>
              </div>
            </b-collapse>
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
export default {
  data() {
    return {
      isActive: false,

      isOpen: 0,
      collapses: [
        {
          title: 'Petunjuk Transfer Virtual Account',
          text:
            'Pilih Transaksi Lainnya. <br/>Pilih Pembayaran > Pembayaran Lainnya. <br/>Pilih Virtual Account. <br/>Masukkan kode bayar (no. Virtual Account), kemudian pilih Benar. <br/>Periksa informasi yang tertera di layar. Pastikan Merchant adalah Shopee, total tagihan sudah benar, dan username Anda {username}. Jika benar, pilih Benar.',
        },
        {
          title: 'Petunjuk Transfer KlikBCA',
          text: 'Text 2',
        },
        {
          title: 'Petunjuk Transfer m-BCA',
          text: 'Text 3',
        },
      ],
    }
  },
}
</script>

<style>
.BREADCRUMB {
  margin: 0 auto;
}
.BREADCRUMB li {
  letter-spacing: 1.5px;
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
