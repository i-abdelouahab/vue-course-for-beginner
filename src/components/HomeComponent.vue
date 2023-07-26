<template>
  <SideBar />

    <div>
      <input v-model="fullName" type="text" name="name" id="">
    </div>

    <div v-if="fullName=='Jojo'">
      <p>Hello {{ fullName }}, you're amazing 🌸</p>
    </div>
    <div v-else-if="fullName=='Ismail'">
      <p>Hello {{ fullName }}, you're not amazing</p>
    </div>
    <div v-else>
      <p>Hello {{ fullName }}, you're a robot</p>
    </div>

    <button @click="displayAlert">Display alert 1</button>
    <button v-on:click="displayAlert">Display alert 3</button>

    <center><table border="1">
      <thead>
        <th>ID</th>
        <th>Nom</th>
        <th>Prénom</th>
        <th>Age</th>
        <th>Centres d'intérêt</th>
      </thead>
      <tbody>
        <tr v-for="student in students" :key="student.id">
          <td>{{ student.id }}</td>
          <td>{{ student.nom }}</td>
          <td>{{ student.prenom }}</td>
          <td>{{ student.age }}</td>
          <td>
            <ul v-for="(hoby, index) in student.interests" :key="index">
              <p>{{ hoby }}</p>
            </ul>
          </td>
        </tr>
      </tbody>
    </table>
  </center>

</template>

<script>
import SideBar from './SideBar.vue';
export default {
    name: "HelloComponent",
    props: {
        msg: String
    },
    components: {
      SideBar,
    },
    data() {
      return {
        fullName: '',
        students : [
          {
            id: 1,
            prenom: "Hajar",
            nom: "Ben Stitou",
            age: 23,
            interests: ["Design", "Voyage", "Natation", "Lecture"]
          },
          {
            id: 2,
            prenom: "Ismail",
            nom: "Abdelouahab",
            age: 23,
            interests: ["Voyage", "Coding", "Complicating things", "Camping"]
          },
        ]
      }
    },
    methods: {
      displayAlert: function() {
        alert("Hello "+this.students[0].prenom+", you're hyper beautiful!")
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
