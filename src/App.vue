<template>
  <p>-----------------Template-------------------</p>
<h1> {{ nama }}</h1>
<h4>{{ noAbsen }}</h4>
<div v-html="rombel"></div>
<p>-----------------Data Binding-------------------</p>
<button v-if="show" :disabled="nonaktif">Button</button>
<h1 v-bind="property">Meng</h1>
<form :method="formMethod">
</form>
{{ count == 0 ? count + 1 : count + 2 }}
<button v-if="show">Show</button>

<div v-if="count == 1">
  Kondisi ketika count 1
</div>

<div v-else-if="count == 2">
  Kondisi ketika count 2
</div>

<div v-else="count">
  Kondisi ketika count lebih dari 2
</div>

<p>----------Computed dan methdos--------------</p>
<button @click="counterNumber">{{ counterButton }}</button>
<button @click ="countComputed">Computed</button>

  <input :type="typeInput">
<button @click="showPassword">show Password</button>

<p>----------class dan style--------------</p>
<ul>
  <li class="fs" :class="{
    active:isActive,
    fs  :isActive
  }">
    test
  </li>

</ul>
<button @click="ubahWarna">Ubah Warna</button>

<p>----------list rendering--------------</p>
<ul>
  <li v-for="(item, index) in daftarNama">{{ item }} |  {{ index+1 }}</li>
</ul>

<p>----------V-model--------------</p>
<input type="text" v-model="inputKelas">
{{ inputKelas }}
</template>

<script>
export default {
  data(){
    return {
      inputKelas: '',
      daftarNama: ['Topaz & Numby', 'Danheng IL', 'Hao Hao'],
      counterButton: 1,
      numberComputed: 'Wanwan adek kaka sama sukaesih bejir',
      count:2,
      nama: 'Komang',
      noAbsen: 14,
      rombel: 'PPLG XI-4',
      nonaktif: true,
      property: {
        id:1,
        class: 'color'
      },
      typeInput: 'password',
      formMethod: 'post',
      show: true,
      isActive: true
    }
  },
  methods:{
    counterNumber(){
      this.counterButton += 1;
    },
    showPassword(){
      if(this.typeInput == 'password'){
        this.typeInput = 'text'
      }else{
        this.typeInput = 'password'
      }
    },
    ubahWarna(){
      if(this.isActive == true){
        this.isActive = false;
      }else{
        this.isActive = true;
      }
    }
  },
  computed: {
    countComputed(){
      alert(this.numberComputed)
    }
  }
}
</script>

<style>
*{
 text-align: center;
}
li{
  list-style-type: none;
}
.color{
  color: red;
}
.fs{
  font-size: 50px;
}
.active {
  color: blueviolet;
}
</style>