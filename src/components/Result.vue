<template>
    <div>
        <h4>{{ result }} </h4>
        <h6>{{ calcMark }}</h6>
    </div>
</template>


<script>
export default {
    props: ['result'],
    name: 'result',
    computed: {
        calcMark() {
            if (this.result < 350 ) {
                return "The next Flash !!";
            } 
            else if (this.result > 350 && this.result < 500 ) {
                return "You are fast";
            }
            else {
                return "You SLOW";
            }
        }
    }
}
</script>