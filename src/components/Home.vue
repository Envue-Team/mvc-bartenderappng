<template>
    <div>
        <p>Home Page</p>
        <!--        <v-card max-width="500">-->
        <!--          <v-card-title>Your order ${{getTotalCost}}</v-card-title>-->
        <!--          <v-list-item-group>-->
        <!--              <v-list-item v-for="cocktail in order" :key="cocktail">-->
        <!--                <template v-slot:default="{ active }">-->
        <!--                    <v-col cols="2">-->
        <!--                          <v-select-->
        <!--                                :items="amount"-->
        <!--                                :value="cocktail.count"-->
        <!--                                @change="updateCount($event, cocktail)"-->
        <!--                        ></v-select>-->
        <!--                      </v-col>-->
        <!--                    <v-col cols="5">-->
        <!--                        <v-list-item-content>-->
        <!--                            <v-list-item-title>-->
        <!--                                {{cocktail.cocktail}} - -->
        <!--                                ${{getCost(getPrice(cocktail), cocktail.count)}}-->
        <!--                            </v-list-item-title>-->
        <!--                            <v-list-item-subtitle>{{cocktail.status}} - {{getPrice(cocktail)}}</v-list-item-subtitle>-->
        <!--                        </v-list-item-content>-->
        <!--                    </v-col>-->
        <!--                    <v-col cols="3">-->
        <!--                        <v-btn text-->
        <!--                               color="red"-->
        <!--                               v-on:click="removeSelection(cocktail)"-->
        <!--                        >-->
        <!--                            <v-icon>mdi-delete</v-icon>-->
        <!--                        </v-btn>-->
        <!--                    </v-col>-->
        <!--                </template>-->
        <!--              </v-list-item>-->
        <!--          </v-list-item-group>-->
        <!--          <v-row>-->
        <!--            <v-card-actions>-->
        <!--              <v-btn color="primary" v-on:click="cancelOrder">Cancel Order</v-btn>-->
        <!--            </v-card-actions>-->
        <!--            <v-card-actions>-->
        <!--              <v-btn color="red" v-on:click="updateOrder">Update Order</v-btn>-->
        <!--            </v-card-actions>-->
        <!--          </v-row>-->
        <!--        </v-card>-->
        <!--<v-row>-->

        <!--  <v-card max-width="300">-->
        <!--    <v-list-item-group>-->
        <!--      <v-list-item v-for="item in cocktails" :key="item">-->
        <!--        <template v-slot:default="{ active }">-->
        <!--          <v-list-item-action>-->
        <!--            <v-checkbox-->
        <!--                    :input-value="active"-->
        <!--                    color="primary"-->
        <!--                    :value="item.cocktail"-->
        <!--                    v-model="selected"-->
        <!--            ></v-checkbox>-->
        <!--          </v-list-item-action>-->

        <!--          <v-list-item-content>-->
        <!--            <v-list-item-title>{{item.cocktail}} - {{item.price}}</v-list-item-title>-->
        <!--            <v-list-item-subtitle>{{item.description}}</v-list-item-subtitle>-->
        <!--          </v-list-item-content>-->
        <!--        </template>-->
        <!--      </v-list-item>-->
        <!--    </v-list-item-group>-->
        <!--    <v-card-actions>-->
        <!--      <v-btn color="primary" v-on:click="addToOrder">Add Selections</v-btn>-->
        <!--    </v-card-actions>-->
        <!--  </v-card>-->
        <!--</v-row>-->
    </div>
</template>

<script>
    // @ is an alias to /src
    // const USER_URI = 'http://localhost:4000/users/uniqueemail4';
    // const COCKTAILS_URI = 'http://localhost:4000/cocktails';
    // const UPDATE_ORDER_URI = 'http://localhost:4000/users/uniqueemail4/order/update';
    export default {
        name: 'Home',
        data: () => ({
            // error: '',
            // user: Object,
            // cocktails: [],
            // selected: [],
            // order: [],
            // totalCost: 0,
            // amount: [1,2,3,4,5,6,7,8,9,10],
        }),
        mounted() {
            // fetch(USER_URI)
            //     .then((response) => response.json())
            //     .then((result) => {
            //         this.user = result;
            //         this.order = result.order;
            //     });
            //
            // fetch(COCKTAILS_URI)
            //     .then((response) => response.json())
            //     .then((result) => {
            //         return this.cocktails = result
            //     });

        },
        computed: {
            //     getTotalCost(){
            //         const cost = this.order.map((order)=> {
            //             let amount = 0;
            //             this.cocktails.filter((item)=> {
            //                 amount = parseFloat(item.price.replace("$",""));
            //                 return item.cocktail == order.cocktail;
            //             });
            //             return amount * order.count;
            //         });
            //         return cost.reduce((a, b) => {return a + b;}, 0);
            //     },
            // },
            // methods: {
            //   getPrice(cocktail){
            //     const selection = this.cocktails.filter((item)=>
            //     {return item.cocktail == cocktail.cocktail});
            //     if(selection[0] !== undefined){
            //         return selection[0].price;
            //     }
            //   },
            //   getCost(price, count){
            //     const value = parseFloat(price.replace("$", ""));
            //     return value * count;
            //   },
            //
            //   removeSelection(item){
            //       this.user.order.splice(this.user.order.indexOf(item), 1);
            //   },
            //     updateCount(value, cocktail){
            //       cocktail.count = value;
            //     },
            //     updateOrder(){
            //     const requestOptions = {
            //         method: "POST",
            //         headers: { "Content-Type": "application/json" },
            //         body: JSON.stringify(this.user)
            //     };
            //       fetch(UPDATE_ORDER_URI, requestOptions)
            //           .then((response) => response.json());
            //     },
            //     addToOrder(){
            //       this.user.order.forEach((order)=>{
            //           if(this.selected.indexOf(order.cocktail) > -1){
            //               this.selected.splice(this.selected.indexOf(order.cocktail), 1);
            //           }
            //       });
            //       this.selected.forEach((selection)=>{
            //           const addition = this.cocktails.filter((cocktail)=>
            //           {return cocktail.cocktail == selection});
            //           addition[0].count = 1;
            //           console.log(addition[0]);
            //           this.user.order[this.user.order.length] = addition[0];
            //       });
            //       this.$set(this.order, 'order', this.user.order );
            //     },
            //     cancelOrder(){
            //       console.log("cancel called");
            //       this.user.order = [];
            //       this.order = [];
            //         this.$set(this.order, 'order', this.user.order);
            //     },
        }
    }
</script>

<style scoped>

</style>