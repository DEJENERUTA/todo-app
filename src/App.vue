
<script>
export default {
  data () {
    return {
      title: 'Todo List',
      items: [
        'Buy milk',
        'Buy bread',
        'Buy coffee'
      ],
      newItem: ''
    }
  },
  methods: {
    addItem () {
      this.items.push(this.newItem)
      this.newItem = ''
    }
  }
}
</script>
<template>
<h1>{{ title }}</h1>
<p>This is a simple todo list</p>
<ul>
<li v-for="(item, index) in items" :key="index">

 {{ item }}
  </li>
</ul>
<input v-model="newItem" @keyup.enter="addItem" />
<button @click="addItem">Add</button>
<span>{{ item }}</span>
<button @click="deleteItem(index)">Delete</button>
</template>

<style>
#app {
font-family: Avenir, Helvetica, Arial, sans-serif;
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
text-align: center;
color: #2c3e50;
margin-top: 60px;
}

h1 {
border-bottom: 1px solid #ddd;
display: inline-block;
padding-bottom: 10px;
}
ul {
list-style-type: none;
}
li {
margin-bottom: 10px;
}
input {
background: #2c3e50;
color: #fff;
border: none;
padding: 10px;
font-size: 16px;
border-radius: 5px;
margin-left: 15px;
}

button {
background: #2c3e50;
color: #fff;
border: none;
padding: 10px;
font-size: 16px;
border-radius: 5px;
margin-left: 15px;
}

</style>
