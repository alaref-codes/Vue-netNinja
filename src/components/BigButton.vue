<template>
    <div class="cont">
        <button :style="{ top: top, right: right }" v-show="showBig" class="big" ref="bloc"  v-on:click="stopTimer"  >
            Press Fast!!
        </button>
    </div>
</template>


<script>
export default {
    name: 'big',
    props: ['delay'],
    data() {
        return {
            showBig: false,
            timer: null,
            reactionTime: 0,
            top: 54,
            right: 24,
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBig = true;
            console.log(this.$refs.bloc);

            // this.$refs.bloc.style.top = 400;
            // this.$refs.bloc.style.right = 200;

            this.startTimer();
        } , this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10;
            }, 10);
        },
        stopTimer() {
            clearInterval(this.timer);
            this.$emit('end' , this.reactionTime)
        }
    }
}
</script>


<style scoped>

.cont {
    border: 5px solid black;
    position: relative;
    padding: 0px;
    width: 400px;
    height: 400px;
    margin: auto;
    margin-top: 30px;
    text-align: center;
    border-radius: 5px;
    display: block;

}

.big {
    background-color: darkturquoise;
    position: absolute;
    padding: 20px;
    width: 70px;
    height: 70px;
    margin: auto;
    text-align: center;
    border-radius: 5px;
}
</style>