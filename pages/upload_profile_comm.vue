<template>
  <section>
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
