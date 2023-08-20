<template>
  <transition name="modal-fade">
    <div class="modal-backdrop" >
      <div class="modal"
        role="dialog"
        aria-labelledby="modalTitle"
        aria-describedby="modalDescription"
        key="modal-component"
      >
        <section
          class="modal-body"
          id="modalDescription"
        >
            <img class="main-img" :src="imgSrc" />

            <div class="annotation">
                <p class="about">{{ aboutText }}</p>

                <p v-if="imgColl.length > 1" class="l-r">Use left and right arrow keys to browse through set or click on the dots. Close w/ Esc.</p>

                <section class="key">
                    <button class="key-item" v-for="img, index in imgColl" @click="goToImg(index)" :key="img.src" :class="{ 'active': index === activeImgIndex}" />
                </section>

                <button
                    type="button"
                    @click="close"
                    aria-label="Close modal"
                >
                    Close Window
                </button>
            </div>
        </section>
      </div>
    </div>
  </transition>
</template>

<script>
  export default {
    name: 'Modal',
    props: [
        'imgSrc',
        'aboutText',
        'imgColl',
        'activeImgIndex',
    ],
    mounted() {
        document.addEventListener('keydown', (event) => {
            if (event.key === 'Escape') {
                this.close();
            }
        });
    },
    methods: {
      close() {
        this.$emit('close');
      },
      goToImg(index) {
        this.$emit('goToImg', index);
      },
    },
  };
</script>

<style scoped lang="scss">
$col1: #54478c;
$col2: #2c699a;
$col3: #0db39e;
$col4: #83e377;
$col5:#f29e4c;
$col6: #06365c;

.main-img {
    width: 100%;
    height: 100%;
}
  .modal-backdrop {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.7);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 100;
  }

  .modal {
    background: rgba(0, 0, 0, 0.7);
    box-shadow: 2px 2px 20px 1px;
    overflow-x: auto;
    display: flex;
    flex-direction: column;
    width: 80vw;
    height: 80vh;
    color: palegreen;
    position: fixed;
  }

  .modal::-webkit-scrollbar {
      width: 15px;
    }

  .modal::-webkit-scrollbar-track {
    background: rgba(0, 0, 0, 0.3);
    border-radius: 10px;

    @media screen and (prefers-color-scheme: dark) {
      background: rgba(255, 255, 255, 0.3);
    }
  }

  .modal::-webkit-scrollbar-thumb {
    background-color: palegreen;
    border-radius: 10px;

    @media screen and (prefers-color-scheme: dark) {
      background: rgba(palegreen, 0.8);
    }
  }

  .modal-header,
  .modal-footer {
    padding: 15px;
    display: flex;
  }

  .modal-header {
    position: relative;
    border-bottom: 1px solid #eeeeee;
    justify-content: space-between;
  }

  .modal-body {
      position: relative;

      .about {
          background-color: rgba(0, 0, 0, 0.6);
          display: inline-block;
          padding: 0.5rem 10px;
          color: white;
      }
  }

  .modal-footer {
    border-top: 1px solid #eeeeee;
    flex-direction: column;
  }

  .modal-body {
    position: relative;
    padding: 20px 10px;
  }

  .btn-close {
    position: absolute;
    top: 0;
    right: 0;
    border: none;
    font-size: 20px;
    padding: 10px;
    cursor: pointer;
    font-weight: bold;
    color: #4AAE9B;
    background: transparent;
  }

  .btn-green {
    color: white;
    background: #4AAE9B;
    border: 1px solid #4AAE9B;
    border-radius: 2px;
  }

  .modal-fade-enter,
  .modal-fade-leave-to {
    opacity: 0;
    transform: translateY(-20px);
  }

  .modal-fade-enter-active,
  .modal-fade-leave-active {
    transition: opacity .5s ease;
    transform: translateY(0);
  }

  .annotation {
      position: fixed;
      top: 50%;
      width: 40%;
      background-color: rgba(0, 0, 0, 0.6);
      padding-bottom: 20px;
      max-width: 280px;

      .l-r {
        margin: 0 0 1rem 0;
        background-color: rgba(0, 0, 0, 0.6);
        padding: 0.5rem 0;
      }

      button {
          margin: 10px auto 0 auto;
          width: 200px;
          background-color: palegreen;
          color: black;
          transition: all 0.5s;

          &:hover {
              background-color: white;
          }
      }

      p {
        line-height: 1.5;
      }
  }

  .key {
      margin: 0 auto;
      display: flex;
      justify-content: space-evenly;
      width: 50%;
      transition: all 0.2s;

      .key-item {
          height: 20px;
          width: 20px;
          border-radius: 50%;
          display: block;
          background-color: white;
          border: 2px solid rgba(0, 0, 0, 0.7);
          padding: 0;

          &.active {
              background-color: $col4;
              border-color: rgba(0, 0, 0, 0.4);
          }
      }
  }
</style>