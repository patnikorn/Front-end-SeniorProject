<template>
  <div>
    <v-app-bar color="grey lighten-5" dense flat dark outlined>
      <v-toolbar-title>COMPLAINT</v-toolbar-title>
    </v-app-bar>
    <v-container>
      <v-row justify="center">
        <v-col cols="12">
          <div class="mt-8 text-primary text-title text-center">
            ยื่นเรื่องย้ายกลุ่มวิชา
          </div>
        </v-col>
        <v-col cols="12">
          <v-form class="pt-5 pb-0">
            <v-text-field
              v-model="form.complaintFirstName"
              label="ชื่อ (กรุณาใส่คำนำหน้า)"
              outlined
              dense
            ></v-text-field>
            <v-text-field
              v-model="form.complaintLastName"
              label="นามสกุล"
              outlined
              dense
            ></v-text-field>
            <v-text-field
              v-model="form.complaintStudentId"
              label="รหัสนักศึกษา"
              outlined
              dense
            ></v-text-field>
            <v-textarea
              outlined
              v-model="form.complaintText"
              label="เหตุผลที่ขอย้ายกลุ่มวิชา"
            ></v-textarea>
            <v-btn
              depressed
              color="second"
              dark
              class="w-100 mt-5 my-btn"
              @click="submit"
              >ยื่นเรื่องย้าย</v-btn
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
        complaintFirstName: "",
        complaintLastName: "",
        complaintStudentId: "",
        complaintText: "",
      },
    };
  },
  methods: {
    validate() {
      let validated = true;
      const errors = [];
      const validatorField = [
        "complaintFirstName",
        "complaintLastName",
        "complaintStudentId",
        "complaintText",
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
    submit() {
      const data = {
        userLineId: "0001",
        complaintFirstName: this.form.complaintFirstName,
        complaintLastName: this.form.complaintLastName,
        complaintStudentId: this.form.complaintStudentId,
        complaintText: this.form.complaintText,
      };
      if (this.validate()) {
        this.$store.dispatch("getComplaint", this.form);
        // this.$router.push("/information/page2");
        Axios.post("http://localhost:4000/complaint",data).then((res) =>
        console.log(res.data.data)
      );
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
