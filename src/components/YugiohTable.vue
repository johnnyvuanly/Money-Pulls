<template>

    <h2>Yu-Gi-Oh Card Price Tracker</h2>

    <div class="container">
        <table class="table table-hover">
            <thead>
                <tr>
                    <th scope="col">Set</th>
                    <th scope="col">Price High</th>
                    <th scope="col">Price Low</th>
                    <th scope="col">Updated At</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="card in cards" v-bind:key="card.status">
                    <th scope="row">{{card.data.status}}</th>
                    <td>{{card.status}}</td>
                    <td>{{card.status}}</td>
                    <td>{{card.status}}</td>
                </tr>
            </tbody>
        </table>
    </div>

</template>

<script>

    import axios from 'axios';

    export default {
        name: 'YugiohTable',
        // Place to keep our data
        data() {
            return {
                cards: null,
            }
        }, 
        // Make API calls
        mounted () {
            axios
                .get('http://localhost:8080/api/get_card_prices/dark magician')
                .then((response) => (this.cards = response.status))
        }
    };

</script>

<style>
    h2 {
        margin-bottom: 5%;
    }
</style>