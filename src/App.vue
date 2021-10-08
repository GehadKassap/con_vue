<template>
<div><pre>{{formValues}}</pre></div>
<form class="w-75 m-auto my-5" @submit.prevent="submitForm">
  <div class="mb-3">
    <label  class="form-label">Name </label>
    <input type="text" id="name" class="form-control" v-model.trim.lazy="formValues.name">
  </div>
    <div class="mb-3">
    <label  class="form-label">Phone </label>
    <input type="number" id="phone" class="form-control" v-model.number="formValues.phone">
  </div>
    <div class="mb-3">
    <label  class="form-label">Desc </label>
    <textarea type="text" class="form-control" id="desc" 
    v-model="formValues.desc"> </textarea>
  </div>
 
  <div class="mb-3">
     <label  class="form-label">Country </label>
    <select class="form-select" v-model="formValues.country">
        <option selected>Open this select menu</option>
        <option value="Egpty">Egpty</option>
        <option value="Italy">Italy</option>
        <option value="Turkey">Turkey</option>
   </select>
  </div>

   <div class="mb-3">
      <label  class="form-label">Programming Language </label>
    <select class="form-select" multiple v-model="formValues.progLang">
        <option selected>Open this select menu</option>
        <option value="Php">Php</option>
        <option value="javascript">javascript</option>
        <option value="c++">c++</option>
        <option value="java">java</option>
        <option value="python">python</option>
   </select>
  </div>

            <div class="mb-3">

              <div class="form-check">
                  <input v-model="formValues.isWork" true-value="yess" false-value="noo" class="form-check-input" type="checkbox" id="work">
                  <label class="form-check-label" >
                    Are You Work?
                  </label>
                </div>

              </div>

        <div class="mb-3">
         <label >Choose Skilles</label>
          <div class="form-check">
              <input value="football" v-model="formValues.skilles" class="form-check-input" type="checkbox" id="work">
              <label class="form-check-label" >
                football
              </label>
          </div>
          <div class="form-check">
              <input value="tennis" v-model="formValues.skilles" class="form-check-input" type="checkbox" id="work">
              <label class="form-check-label" >
                tennis
              </label>
          </div>
          <div class="form-check">
              <input value="boxing" v-model="formValues.skilles" class="form-check-input" type="checkbox" id="work">
              <label class="form-check-label" >
                boxing
              </label>
          </div>
      </div>
  
<div class="mb-3">
  <label> change age range</label>
      <div class="form-check">
      <input type="radio" class="form-check-input" value="10-20"  v-model="formValues.ageRange">
      <label class="form-check-label" >
       20-30
      </label>
    </div>
    <div class="form-check">
      <input class="form-check-input" type="radio"  value="30-40"  v-model="formValues.ageRange">
      <label class="form-check-label">
       30-40
      </label>
    </div>
</div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
<!-- text inerpolation -->
 <!-- <h1 v-bind:id="vueId">{{ name }}</h1> -->
 <!-- <p v-text="desc"></p> -->
 <!-- <div v-html="appendHtml"></div> -->
<!-- <p v-bind:class="vueClass">test class binding</p> -->
<!-- <p>{{1+2+3}}</p>
<h1>result of add method is {{ add()}}</h1>
<h1>result of add method is {{ addThree(1,2,3)}}</h1>
<h2>output of bind data and methods prop is {{Counter(10)}}</h2> -->
<h2> {{name}}</h2>
<button v-on:click="name='Vue Js'">change Name</button>
<!-- <h2> {{test}}</h2>
<button v-on:click="changeTest">change Test</button>

<h2> {{count}}</h2>
<button v-on:click="incremnet()">Increment</button>
<button v-on:click="incremnet(5)">Increment5</button>
<button v-on:click="decrement(5)">Decrement5</button>

<button v-on:click="decrement()">Decrement</button> -->
</template>

<script>

export default {
  name: 'App',
  methods:
  {
    submitForm()
    {
      //event
      // event.preventDefault();
      console.log(this.formValues);
    },
    changeTest(event)
    {
      console.log(event);
       return this.test = "vUE";
    },
    incremnet(num=1)
    {
        this.count +=num;
    },
      decrement(num=1)
    {
        this.count -=num;
    },
  //  add()
  //  {
  //    return 1+2+3;
  //  },
  //  addThree(n1,n2,n3)
  //  {
  //     return n1+n2+n3;
  //  },
  //  Counter(num)
  //  {
  //    return num* this.counter;
  //  },
  },
  data()
  {
   return{
     formValues :
     {
       name : '',
       desc : '',
       country:'',
       progLang : [],
       isWork :"noo",
       skilles : [],
       ageRange: '',
       phone : null,
     },
     test :'TEST',
     count:0,
     name :'gehad',
    //  counter :5,
  //   name:"first vue session",
  //   desc : "in this session we will learn how to install vue and structure of vue.js",
  //   appendHtml : "this is test for <b><i>bold tag from script block</i></b>",
  //   vueId : "vue",
  //   vueClass : "vue-class"
   }

  }
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#vue
{
  color:red;
  font-size: 30px;
}
.vue-class 
{
  color:green
} */
</style>
