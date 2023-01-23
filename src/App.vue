<template>
  <div>hello {{ datasensor }} {{ datasensor2 }}
  <button @click="getData" class="bg-red-600 p-2 rounded-xl">Ambil Data</button> &nbsp;
  <button @click="getData2" class="bg-red-600 p-2 rounded-xl">Ambil Data 2</button>
  </div>
</template>

<script> //tempat ngoding java script
export default {
  data(){
    return{
      datasensor : "95",
      datasensor2 : "100"
    }
  },
  created(){
    //this.getData()
   // this.getData1()
  },
  methods: {
    //getData1(){
    //  alert('hello')
   // },
    async getData(){
      const data = await fetch("http://localhost:3000/getdata")
      const datajson = await data.json()
      console.log(datajson)
      this.datasensor = datajson.sensor3
    
      
      },
    
      async getData2(){
      const data = await fetch("http://localhost:3000/getdata2")
      const datajson = await data.json()
      console.log(datajson)
      this.datasensor2 = datajson.sensor2
    
      
      }

  },

}
</script>

<style>

</style>