<template>
    <div class="container-score">
            <p v-if="istrue" class="score des">{{ userChoice }} Vs {{ sysChoice }}</p>
        <div class="score">
            {{ userScore }}<small>:User</small> vs {{ sysScore }}<small>:System</small>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Score",
        props: {
          userScore: {
              required: true,
              type: Number
          },
          sysScore: {
              required: true,
              type: Number
            },
            userChoice: {
              required: true
            },
            sysChoice: {
                required: true
            },
            istrue: {
              required: true,
                type: Boolean
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

    .score {
        background-color: lightgrey;
        width: 350px;
        border: 1px solid #000;
        padding: 10px;
        font-size: 35px;
        font-weight: bold;
    }
    .des {
        font-size: 25px;
    }

</style>