<template>
  <div class="album-info">
    <transition name="appear">
      <div v-if="isInfoShown" class="album-info__text">
        <p>Release: {{release}}</p>
        <p>Price: {{price}}</p>
      </div>
    </transition>
    <button class="album-info__btn" @click="toggleInfo">{{isInfoShown ? 'less' : 'more'}} info</button>
  </div>
</template>

<script>
export default {
  name: 'album-info',
  props: {
    release: {
        type: String,
        default: ''
    },
    price: {
        type: String,
        default: ''
    },
  },
  data() {
    return {
      isInfoShown: false
    }
  },
  methods: {
    toggleInfo() {
      this.isInfoShown = !this.isInfoShown;
    }
  }
}
</script>

<style scoped lang="scss">
.album-info {
  &__text {
    font-weight: 500;
  }

  &__btn {
    width: 140px;
    border: none;
    border-radius: 20px;
    background: linear-gradient(137deg, #b9e796 0%, #ffa541 100%);
    transition: background 0.1s ease-out;
    color: white;
    padding: 10px 20px;
    font-weight: 600;
    font-size: 20px;
    cursor: pointer;

    &:hover {
      background: linear-gradient(90deg, #abeb7a 0%, #f59b35 100%);
      box-shadow: 5px 5px 5px 5px rgba(0, 0, 0, 0.04);
    }

    &:active {
      background: linear-gradient(90deg, #9be95f 0%, #f1962d 100%);
    }
  }
}

.appear-enter-active { 
  @media screen and (min-width: 600px) {
    animation: pop-up .8s;
	}
}
.appear-leave-active {
  @media screen and (min-width: 600px) {
    animation: pop-up .8s reverse;
  }
}

@keyframes pop-up {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.05);
  }
  100% {
    transform: scale(1);
  }
}
</style>