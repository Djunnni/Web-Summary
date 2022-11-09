<template>
    <div class="modal" v-if="showModal" @close="showModal == false">
        <h3 slot="header">경고</h3>
        <span slot="footer" @click="closeModal">
            할 일을 입력하세요.
            <i class="closeModalBtn fas fa-times" aria-hidden="true"></i>
        </span>
    </div>
</template>

<script>
export default {
    name: "Modal",
    props:['showModal'],
    methods: {
        closeModal() {
            this.$emit('close-modal');
        }
    }
}
</script>

<style scoped>
.modal {
    background-color: #FFF;
}
</style>