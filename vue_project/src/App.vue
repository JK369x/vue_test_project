<script lang="ts" setup> 
import { ref, onMounted } from 'vue'
const header =  'Shopping List App'
let newItem = ref("")
const newItemHighPriority  = ref(false)
const items = ref([
  {id:1,label:"10 party hats"},
  {id:2,label:"2 board games"},
  {id:3,label:"20 cups"},
])
</script> 


<template className="to-do-list">
  <div className="shopping-list">
    <div className="header">
      <h1>{{ header ? header : 'no welcome' }}</h1>
    </div>
    <p>{{ newItem }}</p>
    <div className="add-item-form">
      <input v-on:keyup.enter="items.push({id:items.length + 1,label: newItem})" v-model="newItem" type="text" placeholder="Add ad item">
      <v-btn  v-on:click="items.push({id:items.length + 1,label: newItem})">
        Save Items
      </v-btn>
    </div>
        <ul >
          <li v-for="item in items" :key="item.id">{{item.label}}</li>
          <!-- same under -->
          <!-- <li  v-for="{id,label} in items" :key="id">{{label}}</li> -->
        </ul>
  </div> 
</template>
<style scoped>
.counter {
  font-size: 0.8rem;
  padding-left: 10px;
  padding-right: 10px;
}
a {
  color: #6cb2eb;
  font-size: 1.25rem;
  transition: all 0.1s ease-in;
  margin-top: 0.5rem;
  display: block;
}
a:hover {
  color: #3490dc;
}
.add-item-form,
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
p{
  color:#22292f
}
.add-item-form input {
  width: 70%;
  border-radius: 3px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.1);
  border: 1px solid #f1f5f8;
  color: #606f7b;
  padding: 0.5rem 0.75rem;
  box-sizing: border-box;
  font-size: 1rem;
  letter-spacing: 0.5px;
  margin: 0.5rem 0;
}
.to-do-list{
  background: #eff8ff;
  height: 100vh;
  width: 100vw;
  font-family: system-ui, BlinkMacSystemFont, -apple-system, Segoe UI, Roboto,
    Oxygen, Ubuntu, Cantarell, Fira Sans, Droid Sans, Helvetica Neue, sans-serif;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0;
  padding: 0;
}
.shopping-list{
  background: #fff;
  padding: 2rem;
  margin: 1rem;
  border-radius: 3px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.12), 0 2px 4px 0 rgba(0, 0, 0, 0.08);
  width: 95%;
  max-width: 900px;
}
.shopping-list > input,
.shopping-list > select {
  width: 100%;
  border-radius: 3px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.1);
  border: 1px solid #f1f5f8;
  color: #606f7b;
  padding: 0.5rem 0.75rem;
  box-sizing: border-box;
  font-size: 1rem;
  letter-spacing: 0.5px;
  margin: 0.5rem 0;
}
ul {
  list-style: none;
  padding: 0;
}

li:hover {
  color: #22292f;
}
a {
  color: #6cb2eb;
  font-size: 1.25rem;
  transition: all 0.1s ease-in;
  margin-top: 0.5rem;
  display: block;
}

a:hover {
  color: #3490dc;
}

li,
p {
  display: flex;
  justify-content: center;
  align-items: center;
  line-height: 1.75;
  letter-spacing: 0.5px;
  color: #3d4852;
  font-size: 1.25rem;
  cursor: pointer;
  transition: all 0.1s ease-in;
}
h1 {
  color: #3d4852;
}
li:hover {
  color: #22292f;
}

li input {
  margin: 0 0.5rem 0;
}
li input {
  margin: 0 0.5rem 0;
}
</style>
