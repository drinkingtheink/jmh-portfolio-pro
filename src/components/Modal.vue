<template>
  <transition name="modal-fade">
    <div class="modal-backdrop" @click="close" >
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
    },
  };
</script>

<style scoped lang="scss">
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
          background-color: rgba(0, 0, 0, 0.4);
          display: inline-block;
          padding: 5px;
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
      top: 60%;
      width: 40%;
      background-color: rgba(0, 0, 0, 0.6);
      padding-bottom: 20px;
      max-width: 380px;

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
  }
</style>