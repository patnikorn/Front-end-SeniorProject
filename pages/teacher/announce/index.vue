<template>
  <div>
    <v-app-bar color="grey lighten-5" dense flat dark outlined>
      <v-toolbar-title>ANNOUNCE</v-toolbar-title>
    </v-app-bar>
    <v-container>
      <v-row justify="center">
        <v-col cols="12" class="pt-5 pb-0">
          <div class="text-primary text-title text-center">
            ประกาศผลกลุ่มวิชา
          </div>
        </v-col>
        <v-col cols="11">
          <p> กลุ่มวิชา "วิทยาการข้อมูล (Data Science)" </p>
          <v-row class="pt-2 pb-0">
            <v-col cols="1"> 1 </v-col>
            <v-col cols="5" md="auto"> นางสาวพัฒนิกร ไถ้เงิน </v-col>
            <v-col cols="3" md="auto"> 61114440449 </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 2 </v-col>
            <v-col cols="5" md="auto"> นายภากร สารีบุตร </v-col>
            <v-col cols="3" md="auto"> 61114440494 </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 3 </v-col>
            <v-col cols="5" md="auto"> นางสาววรรณสกนธ์ โภคสมบูรณ์ </v-col>
            <v-col cols="3" md="auto"> 61114440571 </v-col>
          </v-row>
        </v-col>
        <v-col cols="11">
          <hr />
          <p class="mt-4"> กลุ่มวิชา "นวัตกรรมซอฟต์แวร์ (Software Innovation)" </p>
          <v-row class="pt-2 pb-0">
            <v-col cols="1"> 1 </v-col>
            <v-col cols="5" md="auto"> นายกนต์ธร แก้วอร่าม </v-col>
            <v-col cols="3" md="auto"> 61114440018 </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 2 </v-col>
            <v-col cols="5" md="auto"> นายอนุชา สุภาวงศ์ </v-col>
            <v-col cols="3" md="auto"> 61114440830 </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 3 </v-col>
            <v-col cols="5" md="auto"> นายภัทรพล ผิวเรือง </v-col>
            <v-col cols="3" md="auto"> 61114440472 </v-col>
          </v-row>
        </v-col>
        <v-col cols="11">
          <hr />
          <p class="mt-4"> นักศึกษาที่รอการจัดกลุ่มวิชา </p>
          <v-row class="pt-2 pb-0">
            <v-col cols="1"> 1 </v-col>
            <v-col cols="5" md="auto"> นายกนต์ธร แก้วอร่าม </v-col>
            <v-col cols="3" md="auto"> 61114440018 </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 2 </v-col>
            <v-col cols="5" md="auto"> นายอนุชา สุภาวงศ์ </v-col>
            <v-col cols="3" md="auto"> 61114440830 </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 3 </v-col>
            <v-col cols="5" md="auto"> นายภัทรพล ผิวเรือง </v-col>
            <v-col cols="3" md="auto"> 61114440472 </v-col>
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
