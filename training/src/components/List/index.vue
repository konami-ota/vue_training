<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent max-width="600px">
      <template v-slot:activator="{ on, attrs }">
        <v-btn v-bind="attrs" v-on="on" @click="$emit('openItemForm')">
          Open Dialog
        </v-btn>
      </template>
    </v-dialog>
    <v-card>
      <v-data-table
        :headers="HEADERS"
        :items="UESRS"
        hide-default-footer
        class="elevation-1"
      ></v-data-table>
    </v-card>
  </v-row>
</template>
<style scoped></style>
<script>
export default {
  components: {},
  data() {
    return {
      dialog: false,
      HEADERS: [
        {
          text: "名前",
          value: "name",
        },
        { text: "性別", value: "gender" },
      ],
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
