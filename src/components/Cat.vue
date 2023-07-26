<template>
    <div>
        <div id="selection">
            <button type="button" class="btn" v-on:click="catSize++">+</button>
            <button type="button" class="btn" v-on:click="catSize--">-</button>
        </div>
        <div>
            <img src="../assets/jinx2.gif" class="jinxcat" v-bind:style="{ width: catSize + '%' }">
        </div>
    </div>  
</template>

  <script>

    export default {
        sl: '#selection',
        data () {
            return {
                catSize: 20
            }
        }
    }



  </script>
  <style scoped>
  </style>