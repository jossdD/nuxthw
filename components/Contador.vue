<template>
    <div>

        <h2>{{count}}</h2>

    </div>
</template>

<script>
    export default{
        props:{
            initialValue: {
                required: true,
                type: Number, 
                default: 10,
                description: 'Here you must put the initial value'
            },
            delay:{
                default: 1000,
            },

        },

        data(){
            return { 
                count: 0
            }
        },

        mounted(){
            this.count = this.initialValue;
            this.startCountDown();
        },

        methods:{
            startCountDown(){
                setTimeout(() => {
                    this.count--;
                    this.startCountDown();
                }, this.delay);
            }
        },
    }
</script>

<style>
    h2{
        border-collapse: collapse;
        border: 1px solid black;
        padding:10px;
    }
</style>
