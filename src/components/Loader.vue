<template>
  <div class="loader">
      <h2>I AM DOWNLOADING YOUR FAVOURITE ALBUMS!</h2>
      <div class="spinner">
          <div class="lds-ripple"><div></div><div></div></div>
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
  width: 80px;
  height: 80px;
  margin-block: 40px;
}
.lds-ripple div {
  position: absolute;
  border: 4px solid #fff;
  opacity: 1;
  border-radius: 50%;
  animation: lds-ripple 1.55s cubic-bezier(0, 0.2, 0.8, 1) infinite;
}
.lds-ripple div:nth-child(2) {
  animation-delay: 0.5s;
}
@keyframes lds-ripple {
  0% {
    top: -15px;
    left: 36px;
    width: 0;
    height: 0;
    opacity: 1;
  }
  100% {
    top: 15px;
    left: 0px;
    width: 72px;
    height: 72px;
    opacity: 0;
  }
}

</style>