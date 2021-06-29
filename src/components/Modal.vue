<template>
    <div class="backdrop" @click.self="closePage" >
        <div class="modal" :class="{ sale: theme === 'd' }" >
            <p>{{header}} </p>
        </div>
    </div>
</template>


<script>
export default {
    props: ['header' , 'theme'],
    methods: {
        closePage() {
            this.$emit('close')
        }
    }
}
</script>

<style scoped>
    .modal {
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }

    .backdrop {
        top: 0;
        left: 0;
        position: fixed;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.5) ;
    }

    .modal.sale {
        background-color: crimson;

    }
</style>