<template>
  <div>
    <div class="pokeheader__search__type" @click="showModal">
      <p>Type</p>
      <img
        src="../../public/assets/img/arrow-down.svg"
        alt="Arrow Down"
        :data-rotate="modal"
      />
    </div>
    <ul class="pokeheader__search__list" :data-display="modal">
      <li>
        <img src="../../public/assets/img/types/fire.png" alt="pokemon type" />
        <span>Fire</span>
      </li>
      <li>
        <img src="../../public/assets/img/types/fire.png" alt="pokemon type" />
        <span>Fire</span>
      </li>
      <li>
        <img src="../../public/assets/img/types/fire.png" alt="pokemon type" />
        <span>Fire</span>
      </li>
      <li>
        <img src="../../public/assets/img/types/fire.png" alt="pokemon type" />
        <span>Fire</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
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
.pokeheader__search {
  ul {
    position: absolute;
    background: $whiteColor;
    width: remsize(180);
    top: remsize(48);
    border: remsize(1) solid rgba($color: #000, $alpha: 0.2);
    text-align: center;

    li {
      display: flex;
      align-items: center;
      justify-content: space-between;
      cursor: pointer;
      padding: remsize(8) remsize(15);
      border-bottom: remsize(0.5) solid rgba($color: #000, $alpha: 0.2);
      font-size: remsize(14);

      &:hover {
        background: rgba($primaryColor, 0.8);
        color: $whiteColor;
      }

      img {
        width: remsize(25);
      }
    }
  }
  &__type {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: remsize(178);
    height: remsize(40);
    border-radius: remsize(51);
    background: $primaryColor;
    margin-right: remsize(50);

    p {
      color: $whiteColor;
      font-weight: bold;
    }

    img {
      width: remsize(18);

      &[data-rotate='true'] {
        transform: rotate(180deg);
      }
    }
  }
  &__list {
    display: none;

    &[data-display='true'] {
      display: block;
    }
  }
}
</style>
