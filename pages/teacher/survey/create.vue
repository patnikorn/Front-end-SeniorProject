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
              v-model="form.title"
              label="ชื่อฟอร์ม"
              auto-grow
              outlined
              dense
            ></v-text-field>
            <v-textarea
              outlined
              auto-grow
              v-model="form.subTitle"
              label="คำอธิบายแบบฟอร์ม"
            ></v-textarea>
            <v-divider></v-divider>
            <p class="mt-5 pt-0">กลุ่มวิชาวิทยาการข้อมูล (Data Science)</p>

            <v-text-field
              v-model="form.numberStudentDS"
              label="จำนวน"
              outlined
              dense
              class="mt-0 pt-0"
              type="number"
            />
            <p>กลุ่มวิชานวัตกรรมซอฟต์แวร์ (Software Innovation)</p>
            <v-text-field
              v-model="form.numberStudentSI"
              label="จำนวน"
              outlined
              dense
              class="mt-0 pt-0"
              type="number"
            />
            <v-divider></v-divider>
            <v-textarea
              class="mt-5 pt-0"
              v-model="form.question"
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
              @click="previewform"
              >ดูตัวอย่างฟอร์ม</v-btn
            >
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import Axios from "axios";
export default {
  data() {
    return {
      form: {
        title: "",
        subTitle: "",
        question: "",
        numberStudentDS: "",
        numberStudentSI: "",
        DataScience: true,
        SoftwareInnovation: true,
      },
    };
  },
  methods: {
    validate() {
      let validated = true;
      const errors = [];
      const validatorField = [
        "title",
        "subTitle",
        "question",
        "numberStudentDS",
        "numberStudentSI",
      ];
      validatorField.forEach((field) => {
        if (this.form[field] == "") {
          validated = false;
          errors.push(`${field} ไม่สามารถว่างได้`);
        }
      });
      if (!validated) {
        this.$store.dispatch("setDialog", {
          isShow: true,
          title: "กรอกข้อมูลไม่สำเร็จ",
          message: errors.map((error) => error + "<br />").join(""),
        });
      }
      return validated;
    },
    previewform() {
      this.$router.push("/teacher/survey/preview");
        this.$router.push({
        path: "/teacher/survey/preview",
        query: {title: this.form.title, subTitle: this.form.subTitle, question: this.form.question, numberStudentDS: this.form.numberStudentDS, numberStudentSI: this.form.numberStudentSI},
      });
      // this.$router.push({
      //   path: "/teacher/survey/preview",
      //   query: {title: this.form.title, subTitle: this.form.subTitle, question: this.form.question, numberStudentDS: this.form.numberStudentDS, numberStudentSI: this.form.numberStudentSI},
      // });
      if (this.validate()) {
        // Axios.post("https://server.dssi-ubu.cf/survey", data).then((res) => {
        //   console.log(res.data.data);
        //   this.$router.push("/teacher/survey/preview");
        // });
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.v-form {
  padding: 0 30px;
}
</style>
