<template>
    <div id="clock">
        <h1>Máquina do Tempo</h1><br>
        <p class="time">{{ hours }} : {{ minutes }} : {{ seconds }}</p>
        <div class="machine">
            <div class="adders">
                <button type="button" class="btn" v-on:click="addhrs++">+</button>
                <button type="button" class="btn" v-on:click="addhrs--">-</button>
            </div>
            <div class="adders">
                <button type="button" class="btn" v-on:click="addmin++">+</button>
                <button type="button" class="btn" v-on:click="addmin--">-</button>
            </div>
            <div class="adders">
                <button type="button" class="btn" v-on:click="addsec++">+</button>
                <button type="button" class="btn" v-on:click="addsec--">-</button>
            </div>
        </div>
        <p class="text">{{ addhrs }} : {{ addmin }} : {{ addsec }}</p>
    </div>
</template>

    <script>

    export default {
        name: "DigitalClock",
        data() {
            return {
                addhrs: 0,
                addmin: 0,
                addsec: 0, 
                day: 0,
                month: 0,
                year: 0,
                hours: 0,
                minutes: 0,
                seconds: 0
            }
        },
        mounted() {
            setInterval(() => this.setTime(), 1000)
        },
        methods: {
            setTime() {
                const date = new Date();
                let hours = (date.getHours() + this.addhrs) % 24;
                let minutes = (date.getMinutes() + this.addmin) % 60;
                let seconds = (date.getSeconds() + this.addsec) % 60;
                hours = hours < 0 ? hours % 24 + 24 : hours;
                minutes = minutes < 0 ? minutes % 60 + 60 : minutes;
                seconds = seconds < 0 ? seconds % 60 + 60 : seconds;
                hours = hours <= 9 ? "0" + hours : hours;
                minutes = minutes <= 9 ? "0" + minutes : minutes;
                seconds = seconds <= 9 ? "0" + seconds : seconds;
                this.hours = hours;
                this.minutes = minutes;
                this.seconds = seconds;


                let day = date.getDate();
                let month = date.getMonth();
                let year = date.getFullYear();
                day = day <= 9 ? "0" + day : day;
                month = month <= 9 ? "0" + month : month;
                this.day = day;
                this.month = month;
                this.year = year;
            }
        }
    }

    </script>

<style scoped>
    #clock {
    border-radius: 25px;
    padding: 100px;
    background: radial-gradient(ellipse at center, #0a2e38 0%, #000000 150%);
    background-color: rgb(113, 147, 153);
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    color: #daf6ff;
    text-shadow: 0 0 20px rgb(10, 175, 230),  0 0 20px rgba(10, 175, 230, 0);
    .time {
        letter-spacing: 4px;
        font-size: 90px;
        padding: 5px 0;
    }
    .text {
        font-size: 20px;
        padding: 20px 0 0;
    }
    .adders {
        align-items: center;
        display: inline-block;
        margin-right: 55px;
        margin-left: 55px;
    }
}
</style>