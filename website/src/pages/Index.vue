<template>
      <q-page>

      <hr>
      <form>
        <input v-model="user.vname"/>
        <input v-model="user.nname"/>
        <input v-model="user.klasse"/> <input v-model="user.zweig"/></form>
      <form v-on:submit.prevent="addNewUser">
        <button type="submit">Add Schüler</button>
      </form>
      <ul>
        <li v-for="user in users" :key="user.nname">
          {{user.vname+' '+user.nname+' '+user.klasse+' '+user.zweig}}</li>
      </ul>

      </q-page>
</template>

<script>

export default {
  name: 'PageIndex',
  data() {
    return {
      users: [],
      user: {
        vname: 'Vorname', nname: 'Nachname', klasse: 'Klasse', zweig: 'Zweig',
      },
    };
  },
  methods: {
    addNewUser() {
      this.users.push({
        vname: this.user.vname,
        nname: this.user.nname,
        klasse: this.user.klasse,
        zweig: this.user.zweig,
      });
    },
  },

};

</script>
