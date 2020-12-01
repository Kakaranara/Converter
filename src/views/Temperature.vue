<template>
  <div class="temperature">
    <v-container>
      <v-row>
        <v-col align="center">
          <h2>Temperature Converter</h2>
        </v-col>
      </v-row>
      <v-row>
        <v-spacer></v-spacer>
        <v-col cols="6">
          <v-text-field placeholder="Input Here.." width="10px" type="number" clearable v-model="suhuAwal"></v-text-field>
        </v-col>
        <v-spacer></v-spacer>
      </v-row>
      <v-row>
        <v-spacer></v-spacer>
        <v-col cols="6">
          <v-select :items="items1" label="From" v-model="dari"></v-select>
        </v-col>
        <v-spacer></v-spacer>
      </v-row>
    <hr> <hr>
      <v-row>
        <v-spacer></v-spacer>
        <v-col cols="6">
          <div id="hasil">{{convert() || '...'}}</div>
        </v-col>
        <v-spacer></v-spacer>
      </v-row>
      <v-row>
        <v-spacer></v-spacer>
        <v-col cols="6">
          <v-select :items="items1" label="To" v-model="ke"></v-select>
        </v-col>
        <v-spacer></v-spacer>
      </v-row>
    </v-container>
  </div>
</template>

<script>
  export default {
    data: () => ({
      items1: ['Celcius', 'Fahreinheit', 'Reaumur', 'Kelvin'],
      suhuAwal: '',
      dari: 'A',
      ke: 'B'
    }),
    methods: {
      convert: function(){
        let result;
        if(this.dari == this.ke){
          result = parseFloat(this.suhuAwal);
        }else if(this.dari == 'Celcius'){
          if(this.ke == 'Fahreinheit'){
            result = (parseFloat(this.suhuAwal) * 9 / 5) + 32;
          }else if(this.ke == 'Reaumur'){
            result = (parseFloat(this.suhuAwal) * 4 / 5);
          }else if(this.ke == 'Kelvin'){
            result = parseFloat(this.suhuAwal) + 273.15;
          }
        }else if(this.dari == 'Reaumur'){
          if(this.ke == 'Fahreinheit'){
            result = (parseFloat(this.suhuAwal) * 9 / 4) + 32;
          }else if(this.ke == 'Celcius'){
            result = (parseFloat(this.suhuAwal) * 5 / 4);
          }else if(this.ke == 'Kelvin'){
            result = (parseFloat(this.suhuAwal) * 5 / 4) + 273.15;
          }
        }else if(this.dari == 'Fahreinheit'){
          if(this.ke == 'Reaumur'){
            result = (parseFloat(this.suhuAwal) -32 ) * 4 / 9;
          }else if(this.ke == 'Celcius'){
            result = (parseFloat(this.suhuAwal) - 32 ) * 5 / 9 ;
          }else if(this.ke == 'Kelvin'){
            result = ((parseFloat(this.suhuAwal) - 32 ) * 5 / 9 )+ 273.15;
          }
        }else if(this.dari == 'Kelvin'){
          if(this.ke == 'Reaumur'){
            result = (parseFloat(this.suhuAwal) - 273.15  ) * 4 / 5;
          }else if(this.ke == 'Celcius'){
            result = (parseFloat(this.suhuAwal) - 273.15 )  ;
          }else if(this.ke == 'Fahreinheit'){
            result = ((parseFloat(this.suhuAwal) - - 273.15 ) * 9 / 5 ) + 32;
          }
        }
        if(result == 0){
          return 0;
        }else{
          return result;
        }
      }
    }
  }
</script>

<style scoped>
  #hasil{
    margin-top: 24px;
    border-bottom: 1px solid rgb(46, 46, 46);
  }
</style>

