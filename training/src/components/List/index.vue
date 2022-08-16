<template>
  <div class="list">
    <button @click="$emit('openItemForm', device)">新規作成</button>
    <table id="table">
      <tr>
        <thead>
          <tr>
            <th>名前</th>
            <th>性別</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="user in UESRS" :key="user.id">
            <td>
              {{ user.name }}
            </td>
            <td>
              {{ user.gender }}
            </td>
          </tr>
        </tbody>
      </tr>
    </table>
  </div>
</template>
<style scoped>
.list {
  text-align: center;
}
.list * {
  margin-right: auto;
  margin-left: auto;
}
#table {
  border-collapse: collapse;
  line-height: 1.5;
}
tr:nth-child(1) th {
  background-color: #ddd;
}

th,
td {
  padding: 5px 10px;
  border-bottom: 1px solid black;
}
</style>
<script>
export default {
  components: {},
  data() {
    return {
      UESRS: [
        {
          id: 1,
          name: "山田太郎",
          gender: "男",
        },
        {
          id: 2,
          name: "山田太郎",
          gender: "男",
        },
        {
          id: 3,
          name: "山田太郎",
          gender: "男",
        },
        {
          id: 4,
          name: "山田太郎",
          gender: "男",
        },
        {
          id: 5,
          name: "山田太郎",
          gender: "男",
        },
      ],
    };
  },
};
</script>
