<template>
  <div>
    <v-app-bar color="grey lighten-5" dense flat dark outlined>
      <v-toolbar-title>MORE INFORMATION</v-toolbar-title>
    </v-app-bar>
    <v-container class="pt-0 pb-0">
      <v-row justify="center">
        <v-col cols="12">
          <div class="mt-8 text-primary text-title text-center">
            กรอกข้อมูลเพิ่มเติม
          </div>
        </v-col>
        <v-col cols="12">
          <v-form class="pt-5 pb-0">
            <v-text-field
              v-model="form.userFirstName"
              label="ชื่อ (กรุณาใส่คำนำหน้า)"
              outlined
              dense
            ></v-text-field>
            <v-text-field
              v-model="form.userLastName"
              label="นามสกุล"
              outlined
              dense
            ></v-text-field>
            <v-text-field
              v-model="form.userIdNumber"
              label="รหัสนักศึกษา / รหัสอาจารย์"
              outlined
              dense
              type="number"
            ></v-text-field>
            <v-text-field
              v-model="form.email"
              label="อีเมล์"
              outlined
              dense
              type="email"
            ></v-text-field>
            <v-btn
              depressed
              color="second"
              dark
              class="w-100 mt-5 my-btn"
              @click="submit"
              >บันทึก</v-btn
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
        userFirstName: "",
        userLastName: "",
        userIdNumber: "",
        email: "",
      },
    };
  },
  methods: {
    validate() {
      let validated = true;
      const errors = [];
      const validatorField = [
        "userFirstName",
        "userLastName",
        "userIdNumber",
        "email",
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
        userLineId: "",
        userFirstName: this.form.userFirstName,
        userLastName: this.form.userLastName,
        userIdNumber: this.form.userIdNumber,
        email: this.form.email,
      };
      if (this.validate()) {
        this.$store.dispatch("setInformation", this.form);
        // this.$router.push("/information/page2");
        Axios.post("http://localhost:4000/info",data).then((res) =>
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
