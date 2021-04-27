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
                <tr v-for="card in cards" v-bind:key="card.data[0].print_tag" >
                <th scope="row">{{card.data[0].print_tag}}</th>
                <td>{{card.data[0]}}</td>
                <td>{{card.data[0]}}</td>
                <td>{{card.data[0]}}</td>
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
            }; 
        }, 
        // Make API calls
        created: function() {
            axios
                .get('http://yugiohprices.com/api/get_card_prices/Dark%20Magician')
                // Save our data to cards
                .then(res => { 
                this.cards = res.data;
            })
        }
    }
</script>

<style>
    h2 {
        margin-bottom: 5%;
    }
</style>