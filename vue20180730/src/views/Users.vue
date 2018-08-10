<template>
  <div >

    <h2>Список пользователей</h2>

    <div v-if="!users.lenght" class="alert alert-warning">
      Загрузка...
    </div>
    <user-list v-else :users="users" />
  </div>
</template>

<script>
import axios from 'axios'
import UserList from '@/components/UserList.vue'
export default {
  components: {
    'user-list': UserList
  },
  data: function() {
    return {
      users: []
    }
  },
  mounted: function() {
    this.loadData()
  },
  methods: {
    loadData: function() {
      var self = this
      axios.get('http://localhost:3000/users').then(function(response) {
        self.users = response.data
      })
    }
  }
}
</script>

<style>
</style>
