<template>
  <div class="loader">
      <h2>I AM DOWNLOADING YOUR FAVOURITE ALBUMS!</h2>
      <div class="spinner">
            <div class="lds-ripple">
                <div></div>
                <div></div>
            </div>
      </div>
      <h5>{{ loading_sentences[activeSentence] }}</h5>
  </div>
</template>

<script>
export default {
    name: 'Loader',
    data() {
        return {
            loading_sentences: [
                'downloading them from Napster',
                'have you ever heard about winamp?',
                'this is the sound that we make',
                'using a pen to rewind this musicassette',
            ],
            activeSentence: 0,
        };
    },
    created() {
        setInterval(this.changeSentence, 3500);
    },
    methods: {
        changeSentence() {
            if (this.activeSentence < this.loading_sentences.length -1) {
                this.activeSentence++;
            } else {
                this.activeSentence = 0;
            }
        },
    },
}
</script>

<style scoped lang="scss">
@import '@/styles/globals.scss';
@import '@/styles/vars.scss';
    .loader {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: calc(100vh - 66px);
        width: 100vw;
        color: $clear-text;
    }
    .lds-ripple {
  display: inline-block;
  position: relative;
  margin-block: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.lds-ripple div {
  position: absolute;
  border: 4px solid white;
  width: 80px;
  height: 80px;
  opacity: 1;
  border-radius: 50%;
  animation: lds-ripple 1.8s cubic-bezier(0, 0.8, 0.2, 1) infinite;
}
.lds-ripple div:nth-child(2) {
  animation-delay: .25s;
}
@keyframes lds-ripple {
  0% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
        transform: scale(0);
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

</style>