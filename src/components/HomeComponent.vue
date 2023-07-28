<template>
  <div>
    <button @click="someText='Blalalalalalal'">Hello</button>
    {{ someText }}
    <p>{{ vari }}</p>
  </div>
  <!-- <table>
    <thead>
      <th>Id</th>
      <th>UserID</th>
      <th>Title</th>
      <th>Completed</th>
    </thead>
    <tbody>
      <tr  v-for="test in state.tests" :key="test.id">
        <td>{{ test.id }}</td>
        <td>{{ test.userId }}</td>
        <td>{{ test.title }}</td>
        <td>{{ test.completed }}</td>
      </tr>
    </tbody>
  </table> -->
</template>

<script>
import { onMounted, reactive, ref } from 'vue';
import axios from 'axios';
export default {
    name: "HelloComponent",
    props: {
        msg: String
    },
    components: {
    },
    setup() {
      let someText = ref('Thank you Hajar for attending this formation')
      let vari = ref('')
      const state = reactive({
        tests: {
          userId: '',
          id: '',
          title: '',
          completed: false
        },
      })

      onMounted(() => {
        axios.get("https://jsonplaceholder.typicode.com/todos")
          .then((response) => {
            state.tests = response.data
            console.log(someText.value)
          })
      })

      return {
        state,
        someText,
        vari
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
table{
  padding-top: 4cm;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
