<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale' }">
            <slot>defualt content</slot>
            <span>{{ arrayy[0] }}</span>
            <div class="actions">
                <slot name="links"></slot>    
            </div>
        </div>
    </div>
</template> 

<script>
export default {
    props: ['arrayy', 'theme'],
    methods: {
        closeModal(){
            this.$emit('close')
        }
    }
}


</script>
<style>
.modal h1 {
    color: green;
}

.modal.sale h1 {
    color: rgb(251, 28, 28);
}

.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}

.backdrop {
    top: 0;
    position: fixed !important;
    background: rgb(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}
.modal .actions a {
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}
</style>