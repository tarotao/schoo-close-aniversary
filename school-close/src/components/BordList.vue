<template>
    <li>
        <div>
            <h3 class="user-name">{{ user }}さん</h3>{{ date }}
            <br>{{ message }}
            <hr>
        </div>
    </li>
</template>

<script>
export default {
  name: 'BordList',
  props: [
    'user', 'date', 'message'
  ]
}
</script>

<style scoped>
li {
    list-style: none;
}
.user-name {
  display: inline;
  padding-right: 20px;
}
</style>
