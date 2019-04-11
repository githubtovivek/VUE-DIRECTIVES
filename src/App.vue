<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1 v-vueAppOn:click="executeMe" :style="{color: changeColor}">Directives Exercise</h1>
                <!-- Exercise -->
                <!-- Build a Custom Directive which works like v-on (Listen for Events) -->

            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data: function() {
            return {
                changeColor: 'red'
            }
        },
        directives: {
            vueAppOn: {
                bind(el, bindings, node) {
                    let eventName = bindings.arg;
                    let fn = bindings.value;

                    el.addEventListener(eventName, fn);
                }
            }
        },
        methods: {
            executeMe() {
                this.changeColor = 'green'
            }
        }
    }
</script>

<style>
</style>
