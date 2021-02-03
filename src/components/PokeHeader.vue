<template>
  <section class="pokeheader">
    <div class="modal" :data-show="showModal">
      <img
        src="../../public/assets/img/close.svg"
        alt=""
        @click="toggleModal()"
      />
    </div>
    <img
      src="../../public/assets/img/logo.png"
      alt="logo pokemon"
      class="logo"
    />
    <div class="pokeheader__menu" @click="toggleModal()" :data-show="showModal">
      <img src="../../public/assets/img/menu.svg" alt="" />
    </div>

    <div class="pokeheader__search">
      <dropdown />
      <label for="pokename">
        <input type="text" placeholder="Pesquise aqui" id="pokename" />
        <img src="../../public/assets/img/loupe.svg" alt="" />
      </label>
    </div>
  </section>
</template>

<script>
import Dropdown from './Dropdown.vue'

export default {
  name: 'poke-header',

  data() {
    return {
      showModal: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    }
  },

  components: {
    Dropdown
  }
}
</script>

<style lang="scss" scoped>
.pokeheader {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-top: remsize(40);

  .modal {
    display: none;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.8);
    img {
      width: remsize(22);
      position: absolute;
      top: remsize(25);
      right: remsize(25);
      z-index: 100;
    }
    &[data-show='true'] {
      display: block;
    }
  }

  @include media-md {
    margin-top: remsize(20);
    img {
      width: remsize(110);
    }
  }

  &__menu {
    display: none;
    position: absolute;
    right: remsize(20);
    cursor: pointer;
    img {
      width: remsize(25);
    }
    &[data-show='true'] {
      display: none;
    }
    @include media-md {
      display: block;
    }
  }

  &__search {
    cursor: pointer;
    display: flex;
    align-items: center;
    position: relative;
    margin-top: remsize(40);

    @include media-md {
      display: none;
    }

    label {
      border: remsize(0.5) solid rgba($color: #000, $alpha: 0.3);
      height: 100%;
      border-radius: remsize(15);
      display: flex;
      padding: 0 remsize(10);

      img {
        width: remsize(18);
      }

      input {
        width: remsize(300);
        height: remsize(40);
      }
    }
  }
}
</style>
