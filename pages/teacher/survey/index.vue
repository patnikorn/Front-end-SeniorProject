<template>
  <div>
    <v-app-bar color="grey lighten-5" dense flat dark outlined>
      <v-toolbar-title>SURVEY</v-toolbar-title>
    </v-app-bar>
    <v-container>
      <v-row justify="center">
        <v-col cols="12" class="pt-5 pb-0">
          <div class="text-primary text-title text-center">ฟอร์มแบบสำรวจ</div>
        </v-col>
        <v-col cols="12" class="pt-2 pb-0">
          <v-btn
            small
            depressed
            color="success"
            class="edit-btn"
            @click="addSurvey"
          >
            <v-icon left> mdi-plus-circle-outline </v-icon>
            เพิ่ม
          </v-btn>
          <br />
          <br />
          <v-row justify="center">
            <v-col cols="1"> 1 </v-col>
            <v-col cols="6" md="auto">
              การเลือกกลุ่มวิชา (แขนง) ในสาขาวิทยาการข้อมูลและนวัตกรรมซอฟต์แวร์ ปี 2565
            </v-col>
            <v-col cols="3">
              <v-btn icon color="indigo" @click="editSurvey">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-dialog v-model="deleteSurvey" persistent max-width="290">
                <template v-slot:activator="{ on, attrs }">
                  <v-btn icon small v-bind="attrs" v-on="on" color="error">
                    <v-icon>mdi-delete</v-icon>
                  </v-btn>
                </template>
                <v-card>
                  <v-card-title class="text-primary">
                    ยืนยันการลบ
                  </v-card-title>
                  <v-card-text>คุณแน่ใจหรือว่าต้องการลบฟอร์มนี้?</v-card-text>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn
                      color="indigo"
                      text
                      @click="deleteSurvey = false"
                    >
                      ยกเลิก
                    </v-btn>
                    <v-btn
                      color="error"
                      text
                      @click="deleteSurvey = false"
                    >
                      ยืนยัน
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </v-col>
          </v-row>
          <v-row justify="center">
            <v-col cols="1"> 2 </v-col>
            <v-col cols="6" md="auto">
              การเลือกกลุ่มวิชา (แขนง) ในสาขาวิทยาการข้อมูลและนวัตกรรมซอฟต์แวร์ ปี 2566
            </v-col>
            <v-col cols="3">
              <v-btn icon color="indigo">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-btn icon color="error">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-col>
          </v-row>
          <v-row justify="center">
            <v-col cols="1"> 3 </v-col>
            <v-col cols="6" md="auto">
              การเลือกกลุ่มวิชา (แขนง) ในสาขาวิทยาการข้อมูลและนวัตกรรมซอฟต์แวร์ ปี 2567
            </v-col>
            <v-col cols="3">
              <v-btn icon color="indigo">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-btn icon color="error">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      deleteSurvey: false,
    };
  },
  methods: {
    addSurvey() {
      this.$router.push("/teacher/survey/create");
    },
    editSurvey() {
      this$$router.push("teacher/survey/eedit");
    }
  },
};
</script>

<style lang="scss" scoped>
.edit-btn {
  float: right;
}
</style>
