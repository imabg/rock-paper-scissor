<template>
    <div class="container-score">
        <div class="row">
            <button
                    class="btn btn-outline-primary"
                    @click="userChoice('rock')">
                <i class="fas fa-hand-rock"></i> Rock</button>
            <button
                    class="btn btn-outline-primary"
                    @click="userChoice('paper')">
                <i class="fas fa-hand-paper"></i> Paper</button>
            <button
                    class="btn btn-outline-primary"
                    @click="userChoice('scissor')">
                <i class="fas fa-hand-scissors"></i> Scissor</button>
            <button
                    class="btn btn-outline-danger"
                    @click="userChoice('reset')">
                <i class="fas fa-robot"></i> Reset</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "choices",
        data() {
            return {
              choice: ''
            };
        },
        methods: {
            userChoice(q) {
                this.choice = q;
                this.$emit('userChoice', this.choice);
            }
        }
    }
</script>

<style scoped>

    .container-score {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }

    .btn {
        margin: 11px;
    }

</style>