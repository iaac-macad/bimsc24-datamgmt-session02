<!-- // Script is in some way equivalent to script.js. This is place
to define variables, methods and imports of other Vue compoennts. -->
<script setup>
// Understanding ref article: https://blog.logrocket.com/understanding-vue-refs/#:~:text=Ref%20s%20are%20Vue.,element%20in%20your%20Vue%20instance.
// When ref attribute is added to element, this element then can be referenced
// in template. It is sort of templatecement of getElementById (but better)
//My explanation
import { ref } from "vue";

// Define variables and constants
let count = ref(0);
let name = ref("Anna Del Monaco")
 
const text = ref('Anna'); 
const inputText = ref(''); 

let newColor = ref('');
let color = ref('');

// Define functions
function increment() {
  count.value++;
  console.log(name)


// lifecycle hooks
onMounted(() => {
  console.log(`The initial count is ${count.value}.`)
})

}

// Add an input text in the template and a button with @click. Once the button is clicked, it should call back a function that adds the text to a ref variable and display it
// Color try definition

function changeColor() {

    const elements = document.getElementById("top-bar");
    console.log(elements)
    elements.style.backgroundColor=newColor.value 
}

// Add two input texts in the sidebar and a button with @click. One will collect a selector and the second one a color. Once youpress the button, it should change the color to that css selector.



</script>

<!-- Template is a HTML-based syntax that allows you to bind the rendered DOM elements
with data, objects, functions etc. -->
<template>
  <div id="top-bar">
    <div id="title-container">
      <img class="logo-image" alt="Iaac logo" src="./assets/iaac-white.png" />
      <h2>Digital Tools for Cloud-based Data Management {{ name }}</h2>
    </div>
  </div>

   
    <div id="navbar" class="container">  
        <div id="title">Anna's bootcamp website website</div>
        <div id="logo">
            <img src="./cow.jpg" alt="macad cow">

        </div>
        
    </div>

    <div id="flex">

        <div id="sidebar" class="container"> Sidebar </div>

        <div>
          
   <button id="Add Text" @click="addText">Add Text</button>
   <br><input type="text" v-model="inputText" placeholder="Add Text"/>
    
   <button @click="changeColor">Apply new color</button>
   <br><input type="text" id="textInput" v-model = "newColor" placeholder="color">
  
    
   
  </div>


        <div id="main" class="container"> <p>{{ displayText }}</p> </div>
    </div>


  <div id="content">

    <!-- First example - button -->
    <!-- Here we define what function will be called when button is clicked. -->
    <button @click="increment">Count is: {{ count }}</button>


    <!-- Now we print the value. The syntax to print variable is {{ variable_name }}. -->
    <p style="margin-left: 8px">Count is: {{ count }}</p>
  


  </div>
</template>

<!-- Style is for CSS styling -->
<style scoped>
    
 

body{
  
}

margin:0;


background-color: rgb(59, 59, 59); 
  color: white;

div{

  /* put the borders in the inside of container */
  box-sizing: border-box;
}

img{

  height: 100%;
  width: auto;

}

#navbar{

  height: 50px;
  border-color: red;


}

#flex{
  
  display: flex;
  height: calc(100vh - 50px);
}

#sidebar{
  
  width:30%;
  border-color: blue;

}

#main{
  width:70%;
  border-color: green;

}

#title{
  width: 70%;
  float:left;
}

#logo{
  width: 30%;
  height: 100%;
  float:right;
  text-align: right;

}

.container{

  border-style: dotted;
  border-width: 1px;

  a:active {
  background-color: yellow;
}
  
}

</style>

