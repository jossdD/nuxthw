<template>
    <div style="padding:30px">

        <h3>Devices -> {{devices.length}}</h3>

        <br>
        <table>
            <tr>
                <th>Name</th>
                <th>Id</th>
                <th>userId</th>
                <th>Value</th>
            </tr>

            <tr v-for="device in devices" :key="device.userId"> 
                <td>{{device.name.toUpperCase()}}</td>
                <td>{{device.id}}</td>
                <td>{{device.userId}}</td>
                <td>{{device.value}}c</td>
            </tr>

        </table>

        <br><hr><br>
            Name: <span style="color: green">{{newDevice.name}}</span> <br>
            Id: <span style="color: green">{{newDevice.id}}</span><br>
            userId: <span style="color: green">{{newDevice.userId}}</span> <br>
            Value: <span style="color: green">{{newDevice.value}}</span> <br>
        <br><hr><br>

        Name: <br>
        <input v-model="newDevice.name">
        <br>
        Id: <br>
        <input v-model="newDevice.id">
        <br>

        userId: <br>
        <input v-model="newDevice.userId">
        <br>

        Value: <br>
        <input v-model="newDevice.value">
        <br>

        <button @click="addDevice()">Add device</button>

        <br><hr><br>

        <pre>{{newDevice}}</pre>

    </div>
</template>

<script>
    export default{
        data(){
            return { //codigo importante
                //number: 0,
                devices: [],
                newDevice: {
                    name: '',
                    id: '',
                    userId: '',
                    value: ''
                }
            }
        },

        created(){
            //console.log("Creado -> " + Date.now());
        },

        mounted(){

                //console.log("montado -> " + Date.now());
                //setTimeout(() => {
                this.getDevices();
                //this.increment(); 
           // }, 1000);
        },
        methods: {
            addDevice(){
                //...
                //var obj = JSON.parse()
                this.devices.push(JSON.parse(JSON.stringify(this.newDevice)))
            },

            getDevices(){
                //...
                var response = [
                    {
                         name: "home",
                         id: "7777",
                         userId: "12g42",
                         value: 7
                    },
                    {
                         name: "office",
                         id: "8838",
                         userId: "312",
                         value: 15
                    },
                     {
                         name: "taller",
                         id: "88",
                         userId: "12212",
                         value: 15
                    }
                ];

                this.devices = response;
            }
        }
    }
</script>

<style>
    table, th, td{
        border-collapse: collapse;
        border: 1px solid black;
        padding:10px;
    }
</style>