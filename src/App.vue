<template>
  <v-app>
    <v-main>
      <v-flex class="text-center">
        <v-card-title>Playground</v-card-title>
        <v-card class="scale">
          <v-icon large class="icon">
            mdi-spin
            mdi-gamepad-variant
          </v-icon>
        </v-card>
      </v-flex>
      <v-flex class="text-center">
        <DatePicker
          label="Desc"
          default-date="2010"
          @inner-date="log($event)"
        />
      </v-flex>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  components:{
    DatePicker: () => import("@/components/DatePicker"),
  },
  beforeCreate: function(){
    if (window.matchMedia('(prefers-color-scheme: dark)').matches){
      this.$vuetify.theme.isDark=true
    }
  },
  data: () => ({
    //
  }),
  methods:{
    log(input){
      console.log(input)
    }
  }
};
</script>

<style scoped>
.scale{
  height: 25%;
  width: 25%;
}
</style>
