<template>
  <div>
    <v-app-bar color="grey lighten-5" dense flat dark outlined>
      <v-toolbar-title>CREATE SURVEY</v-toolbar-title>
    </v-app-bar>
    <v-container>
      <v-row justify="center">
        <v-col cols="12">
          <div class="pt-5 pb-0 text-primary text-title text-center">
            สร้างฟอร์มแบบสำรวจ
          </div>
        </v-col>
        <v-col cols="12">
          <v-form class="pt-0 pb-0">
            <v-text-field
              v-model="Title"
              label="ชื่อฟอร์ม"
              auto-grow
              outlined
              dense
            ></v-text-field>
            <v-textarea
              outlined
              auto-grow
              v-model="Subtitle"
              label="คำอธิบายแบบฟอร์ม"
            ></v-textarea>
            <v-divider></v-divider>
            <p class="mt-5 pt-0">กลุ่มวิชาวิทยาการข้อมูล (Data Science)</p>

            <v-text-field
              v-model="numberStudentDS"
              label="จำนวน"
              outlined
              dense
              class="mt-0 pt-0"
              type="number"
            />
            <p>กลุ่มวิชานวัตกรรมซอฟต์แวร์ (Software Innovation)</p>
            <v-text-field
              v-model="numberStudentSI"
              label="จำนวน"
              outlined
              dense
              class="mt-0 pt-0"
              type="number"
            />
            <v-divider></v-divider>
            <v-textarea
              class="mt-5 pt-0"
              v-model="Question"
              label="คำถามที่ไม่ระบุชื่อ"
              auto-grow
              outlined
              dense
            ></v-textarea>
            <v-btn
              depressed
              color="second"
              dark
              class="w-100 mt-5 my-btn"
              @click="next"
              >ดูตัวอย่างฟอร์ม</v-btn
            >
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      DataScience: true,
      SoftwareInnovation: true,
    };
  },
  methods: {
    next() {
        this.$router.push("/teacher/survey/preview");
     
    },
  },
};
</script>

<style lang="scss" scoped>
.v-form {
  padding: 0 30px;
}
</style>
