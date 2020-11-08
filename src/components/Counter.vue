<template>
  <h1>{{ count }}</h1>
  
  <div class="buttons">
    <button 
      @mousedown="sum()" 
      @mouseleave="stop()" 
      @mouseup="stop()"
    > + 
    </button>

    <button 
      @mousedown="sub()" 
      @mouseleave="stop()" 
      @mouseup="stop()"
    > - 
    </button>
  </div>
</template>

<script>
  export default {
    name: 'Counter',

    data() {
      return {
        interval: false,
        count: 0,
      };
    },

    methods: {
      sum() {
        if(!this.interval){
          this.interval = setInterval(() => this.count++, 100);
        }
      },

      sub() {
        if(!this.interval){
            this.interval = setInterval(
              () => this.count > 0 && this.count--, 100);	
          }
      },

      stop(){
        clearInterval(this.interval);
        this.interval = false;
      }
    }
  }
</script>

<style scoped>
  h1 {
    font-size: 64px;
  }

  .buttons {
    display: flex;
    align-items: center;
  }
  
  .buttons button {
    cursor: pointer;

    height: 48px;

    display: flex;
    align-items: center;
    justify-content: center;

    border: none;
    border-radius: 8px;
    background: #42b883;

    color: #fff;
    font-size: 32px;
    font-weight: bold;

    padding: 16px 48px;
    margin-top: 48px;

    transition: background-color 0.2s;
  }

  .buttons button:hover {
    background: #267552;
  }

  .buttons button + button {
    margin-left: 16px;
  }
</style>
