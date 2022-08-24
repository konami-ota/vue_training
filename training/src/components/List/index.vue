<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent max-width="600px">
      <template v-slot:activator="{ on, attrs }">
        <v-btn v-bind="attrs" v-on="on" @click="$emit('openItemForm')">
          新規作成
        </v-btn>
      </template>
      <v-card>
        <v-card-title>
          <span class="text-h5">新規作成</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col cols="12" sm="6" md="4">
                <v-text-field
                  v-model="newName"
                  label="名前"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="6">
                <v-select
                  v-model="newGender"
                  :items="gender"
                  label="性別"
                  required
                ></v-select>
              </v-col>
              <pre>{{ $data }}</pre>
            </v-row>
          </v-container>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" text @click="dialog = false">
            Close
          </v-btn>
          <v-btn color="blue darken-1" text @click="addUser()"> Save </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>

    <v-card>
      <v-data-table
        :headers="HEADERS"
        :items="users"
        hide-default-footer
        class="elevation-1"
        @click:row="editItem"
      >
        <template>
          <v-btn
            class="mx-2"
            fab
            dark
            x-small
            color="error"
            @click="deleteTask(item)"
          >
            <v-icon dark>mdi-minus</v-icon>
          </v-btn>
        </template>
      </v-data-table>
    </v-card>
  </v-row>
</template>
<style scoped></style>
<script>
// import Form from "@/components/List/Form/index.vue";
import { USER } from "@/assets/USER.js";

export default {
  components: {
    // Form,
  },

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
      gender: ["男", "女"],
      users: USER,
      newName: "",
      newGender: "",
    };
  },
  methods: {
    editItem(users) {
      console.log(users);
    },

    addUser: function () {
      console.log(this.newName);
      // let url = new URL("../../assets/USER.js");
      // fetch(url, {
      //   method: "POST",
      //   id: Number(Date.now()).toString(16),
      //   name: this.newName,
      //   gender: this.newGender,
      // })
      //   .then((response) => {
      //     this.statusPost = response.status;
      //     return response.json();
      //   })
      //   .then((data) => {
      //     this.resPost = data;
      //   });
    },
  },
};
</script>
