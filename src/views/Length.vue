<template>
  <div class="length">
    <v-container>
      <v-row>
        <v-col align="center">
          <h2>Length Converter</h2>
        </v-col>
      </v-row>

      <v-row>
        <v-spacer></v-spacer>
        <v-col cols="6">
          <v-text-field placeholder="Input Here.." width="10px" type="number" clearable v-model="lenAwal"></v-text-field>
        </v-col>
        <v-spacer></v-spacer>
      </v-row>

      <v-row>
        <v-spacer></v-spacer>
        <v-col cols="6">
          <v-select :items="items1" label="From"  v-model="dari"></v-select>
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
          <v-select :items="items1" label="To"  v-model="ke"></v-select>
        </v-col>
        <v-spacer></v-spacer>
      </v-row>
    </v-container>
  </div>
</template>

<script>
  export default {
    data: () => ({
      items1: ['Kilometre', 'Meter', 'Mile', 'Centimeter', 'Inch', 'Feet'],
      lenAwal: '',
      dari: 'A',
      ke: 'B'
    }),
    methods: {
      convert: function(){
        let result;
        if(this.dari == this.ke){
          result = parseFloat(this.lenAwal);
        }else if(this.dari == 'Kilometre'){
          if(this.ke == 'Meter'){
            result = parseFloat(this.lenAwal)*1000;
          }else if(this.ke == 'Mile'){
            result = parseFloat(this.lenAwal)/1.609;
          }else if(this.ke == 'Centimeter'){
            result = parseFloat(this.lenAwal)*100000;
          }else if(this.ke == 'Inch'){
            result = parseFloat(this.lenAwal)*39370;
          }else if(this.ke == 'Feet'){
            result = parseFloat(this.lenAwal)*3281;
          }
        }else if(this.dari == 'Meter'){
          if(this.ke == 'Kilometre'){
            result = parseFloat(this.lenAwal)/1000;
          }else if(this.ke == 'Mile'){
            result = parseFloat(this.lenAwal)/1609;
          }else if(this.ke == 'Centimeter'){
            result = parseFloat(this.lenAwal)*100;
          }else if(this.ke == 'Inch'){
            result = parseFloat(this.lenAwal)*39.370;
          }else if(this.ke == 'Feet'){
            result = parseFloat(this.lenAwal)*3.281;
          }
        }else if(this.dari == 'Mile'){
          if(this.ke == 'Kilometre'){
            result = parseFloat(this.lenAwal)*1.609;
          }else if(this.ke == 'Meter'){
            result = parseFloat(this.lenAwal)*1609;
          }else if(this.ke == 'Centimeter'){
            result = parseFloat(this.lenAwal)*160934;
          }else if(this.ke == 'Inch'){
            result = parseFloat(this.lenAwal)*63360;
          }else if(this.ke == 'Feet'){
            result = parseFloat(this.lenAwal)*5280;
          }
        }else if(this.dari == 'Centimeter'){
          if(this.ke == 'Kilometre'){
            result = parseFloat(this.lenAwal)/100000;
          }else if(this.ke == 'Meter'){
            result = parseFloat(this.lenAwal)/100;
          }else if(this.ke == 'Mile'){
            result = parseFloat(this.lenAwal)/160934;
          }else if(this.ke == 'Inch'){
            result = parseFloat(this.lenAwal)/2.54;
          }else if(this.ke == 'Feet'){
            result = parseFloat(this.lenAwal)/30.48;
          }
        }else if(this.dari == 'Inch'){
          if(this.ke == 'Kilometre'){
            result = parseFloat(this.lenAwal)/39370;
          }else if(this.ke == 'Meter'){
            result = parseFloat(this.lenAwal)/39.37;
          }else if(this.ke == 'Mile'){
            result = parseFloat(this.lenAwal)/63360;
          }else if(this.ke == 'Centimeter'){
            result = parseFloat(this.lenAwal)*2.54;
          }else if(this.ke == 'Feet'){
            result = parseFloat(this.lenAwal)/12;
          }
        }else if(this.dari == 'Feet'){
          if(this.ke == 'Kilometre'){
            result = parseFloat(this.lenAwal)/3281;
          }else if(this.ke == 'Meter'){
            result = parseFloat(this.lenAwal)/3.281;
          }else if(this.ke == 'Mile'){
            result = parseFloat(this.lenAwal)/5280;
          }else if(this.ke == 'Centimeter'){
            result = parseFloat(this.lenAwal)*30.48;
          }else if(this.ke == 'Inch'){
            result = parseFloat(this.lenAwal)*12;
          }
        }
        return result;
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