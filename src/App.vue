<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12">
                <br>
                <button class="btn btn-primary" @click="setCurrentCmp('appBlue')">Load Blue Template</button>
                <button class="btn btn-success" @click="setCurrentCmp('appGreen')">Load Green Template</button>
                <button class="btn btn-danger" @click="setCurrentCmp('appRed')">Load Red Template</button>
                <hr>
              <keep-alive>
                <component :is="currentCmp">
                  <template v-slot:blue>
                    <h1>I'm blue</h1>
                  </template>
                  <template v-slot:green>
                    <h1>I'm green</h1>
                  </template>
                  <template v-slot:red>
                    <h1>I'm red</h1>
                  </template>
                </component>
              </keep-alive>
            </div>
        </div>
    </div>
</template>

<script>
    import Blue from './components/Blue.vue';
    import Green from './components/Green.vue';
    import Red from './components/Red.vue';

    export default {
        components: {
            appBlue: Blue,
            appGreen: Green,
            appRed: Red
        },
      data(){
          return{
            currentCmp: ''
          }
      },
      methods:{
          setCurrentCmp(cmp){
            this.currentCmp = cmp;
          }
      }
    }
</script>

<style>
</style>
