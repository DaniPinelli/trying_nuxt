<template lang="html">
    <h1>{{message}}</h1>
</template>

<script>
import axios from 'axios';
import env from '../config/env';
export default {
    name: 'Index',
    data() {
        return {
            message: ''
        };
    },
    created() {
        axios.get(`${env.endpoint}/albums`)
            .then(response => {
                this.message = response.status;
            })
            .catch(error => {
                console.log(error);
            });
    },
}
</script>

<style scoped>

</style>