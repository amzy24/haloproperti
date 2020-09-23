<template>
  <section>
    <section class="MAIN">
      <nuxt />
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
              <a href="" class="has-text-dark">Tentang Kami</a><br />
              <a href="" class="has-text-dark">Layanan Kami</a><br />
              <a href="" class="has-text-dark">Mitra Kami</a>
            </div>
            <div class="column is-half">
              <a href="" class="has-text-dark">Kontak Kami</a><br />
              <a href="" class="has-text-dark">Pusat Bantuan</a>
              <a href="" class="has-text-dark">Kebijakan Privasi</a><br />
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
.FOOTER {
  height: fit-content;
}
.has-background-halo {
  background-color: #f79351;
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
