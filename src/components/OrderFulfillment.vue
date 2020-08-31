<template>
    <v-card>
        <v-card-title>Pending Orders</v-card-title>
        <v-list-item-group>
            <v-list-item v-for="order in drinks">
                <template v-slot:default="{ active }">
                    <v-checkbox
                            :input-value="active"
                            color="primary"
                            :value="generateValue(order)"
                            v-model="completed"
                    ></v-checkbox>

                    <v-list-item-content>
                        <v-list-item-title>{{order.count}} - {{order.cocktail}}</v-list-item-title>
                        <v-list-item-subtitle>{{order.status}}</v-list-item-subtitle>
                    </v-list-item-content>
                </template>
            </v-list-item>
        </v-list-item-group>
        <v-card-actions>
            <v-btn color="primary" v-on:click="updateComplete">Complete</v-btn>
        </v-card-actions>
    </v-card>
</template>

<script>
    const USERS_URI = 'http://localhost:4000/users';

    export default {
        name: "OrderFulfillment",
        data: () => ({
            drinks: [],
            users: [],
            completed: [],
        }),
        mounted() {
            fetch(USERS_URI)
                .then((response) => response.json())
                .then((result) => {
                    this.users = result;
                    this.users.forEach((user) => {
                        user.order.forEach((item) => {
                            item.email = user.email;
                            this.drinks[this.drinks.length] = item;
                        });
                    });
                    this.drinks = this.drinks.filter((drink) => {
                        return drink.status == 'Ordered';
                    });
                });
        },
        methods: {
            updateComplete() {
                this.completed.map((item) => {
                    const spl = item.split("-");
                    return {
                        email: spl[0],
                        cocktail: spl[1]
                    }
                }).forEach((item) => {
                    this.users
                        .filter((user) => {
                            return user.email == item.email;
                        })
                        .forEach((user) => {
                            user.order.forEach((drink) => {
                                if (drink.cocktail == item.cocktail) {
                                    drink.status = "Complete";
                                }
                            });
                            this.updateOrder(user);
                        });
                })
            },
            updateOrder(user) {
                const UPDATE_ORDER_URI = 'http://localhost:4000/users/' + user.email + '/order/update';
                console.log(UPDATE_ORDER_URI);
                const requestOptions = {
                    method: "POST",
                    headers: {"Content-Type": "application/json"},
                    body: JSON.stringify(user)
                };
                fetch(UPDATE_ORDER_URI, requestOptions)
                    .then((response) => response.json());
            },
            generateValue(drink) {
                return drink.email + "-" + drink.cocktail;
            }
        }
    }
</script>

<style scoped>

</style>