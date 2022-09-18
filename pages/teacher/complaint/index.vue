<template>
    <div>
      <v-app-bar color="grey lighten-5" dense flat dark outlined>
        <v-toolbar-title>COMPLAINT</v-toolbar-title>
      </v-app-bar>
      <v-container>
        <v-row justify="center">
          <v-col cols="12" class="pt-5 pb-0">
            <div class="text-primary text-title text-center">
              ยื่นเรื่องย้ายกลุ่มวิชา
            </div>
          </v-col>
          <v-col cols="11">
            <v-row class="pt-2 pb-0">
              <v-col cols="1"> 1 </v-col>
              <v-col cols="3" md="auto"> นางสาวพัฒนิกร ไถ้เงิน </v-col>
              <v-col cols="3" md="auto"> 61114440449 </v-col>
              <v-col cols="3" md="auto"> อยากอยู่กับเพื่อน รู้สึกไม่อยากหนีจากเเพื่อน อยากตามเพื่อนไปตลอด </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </template>
  
  <script>
  export default {
    data: () => ({
      editStudent: false,
      deleteStudent: false,
      subject: "DataScience",
    }),
  };
  </script>
  
  <style lang="scss" scoped>
  .edit-btn {
    float: right;
  }
  </style>
  