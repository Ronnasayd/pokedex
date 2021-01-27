<template>
  <section class="pokeheader">
    <img
      src="../../public/assets/img/logo.png"
      alt="logo pokemon"
      class="logo"
    />
    <div class="pokeheader__search">
      <div class="pokeheader__search__type" @click="showModal">
        <p>Type</p>
        <img
          src="../../public/assets/img/arrow-down.svg"
          alt="Arrow Down"
          :data-rotate="modal"
        />
      </div>
      <ul class="pokeheader__search__list" :data-display="modal">
        <li>Fogo</li>
        <li>Fogo</li>
        <li>Fogo</li>
        <li>Fogo</li>
      </ul>
      <label for="pokename">
        <input type="text" placeholder="Pesquise aqui" id="pokename" />
        <img src="../../public/assets/img/loupe.svg" alt="" />
      </label>
    </div>
  </section>
</template>

<script>
export default {
  name: 'header',
  data() {
    return {
      modal: false
    }
  },
  methods: {
    showModal() {
      this.modal = !this.modal
    }
  }
}
</script>

<style lang="scss" scoped>
.pokeheader {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-top: 40px;

  &__search {
    cursor: pointer;
    display: flex;
    align-items: center;
    position: relative;
    margin-top: 40px;

    ul {
      position: absolute;
      background: white;
      width: 180px;
      top: 48px;
      border: 1px solid rgba($color: #000, $alpha: 0.2);
      text-align: center;

      li {
        cursor: pointer;
        padding: 8px;
        margin: 0 8px;
        border-bottom: 0.5px solid rgba($color: #000, $alpha: 0.2);
        font-size: 14px;
      }
    }

    label {
      border: 0.5px solid rgba($color: #000, $alpha: 0.3);
      height: 100%;
      border-radius: 15px;
      display: flex;
      padding: 0 10px;

      img {
        width: 18px;
      }

      input {
        width: 300px;
        height: 40px;
      }
    }

    &__list {
      display: none;

      &[data-display='true'] {
        display: block;
      }
    }

    &__type {
      display: flex;
      justify-content: space-around;
      align-items: center;
      width: 178px;
      height: 40px;
      border-radius: 51px;
      background: #6e6ce7;
      margin-right: 50px;

      p {
        color: white;
        font-weight: bold;
      }

      img {
        width: 18px;

        &[data-rotate='true'] {
          transform: rotate(180deg);
        }
      }
    }
  }
}
</style>
