<template>
  <table class="table table-hover">
    <thead>
      <tr>
        <th>#</th>
        <th>Имя</th>
        <th>Фамилия</th>
        <th>Активен</th>
        <th>Баланс</th>
        <th>Email</th>
        <th>Телефон</th>
        <th>Зарегистрирован</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in users" :key="item.id">
        <td>#{{ item.id }}</td>
        <td>{{ item.firstName }}</td>
        <td>{{ item.lastName }}</td>
        <td>{{ item.isActive }}</td>
        <td>{{ item.balance }}</td>
        <td>{{ item.email }}</td>
        <td>{{ item.phone }}</td>
        <td>{{ item.registered }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: {
    users: {
      type: Array,
      required: true
    }
  },
  computed: {
    total: function() {
      return this.users.length
    }
  }
}
</script>
