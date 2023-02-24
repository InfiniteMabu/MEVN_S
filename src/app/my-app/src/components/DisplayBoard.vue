<template>
    <div class="display-board">
        <h4>Usuarios Creados</h4>
        <div class="number">
        {{numberOfUsers}}
        </div>
        <div class="btn">
            <button @click='getAllUsers()' type="button" class="btn btn-warning">Todos los usuarios</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'DisplayBoard',
        props: ['numberOfUsers'],
        methods: {
            getAllUsers() {
                this.$emit('getAllUsers')
            }
        }
    }
</script>