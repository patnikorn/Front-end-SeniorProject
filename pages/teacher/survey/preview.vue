<template>
  <div>
    <v-app-bar color="grey lighten-5" dense flat dark outlined>
      <v-toolbar-title>SURVEY</v-toolbar-title>
    </v-app-bar>
    <v-container>
      <v-row justify="center">
        <v-col cols="11">
          <div class="mt-2 text-primary text-title text-center">
            การเลือกกลุ่มวิชา (แขนง) ในสาขาวิทยาการข้อมูลและนวัตกรรมซอฟต์แวร์ ปี
            2565
          </div>
        </v-col>
        <v-col cols="11">
          <div>
            <p>
              ทางหลักสูตรขอสำรวจข้อมูลเบื้องต้น
              เพื่อเตรียมความพร้อมการเลือกกลุ่มวิชา (แขนง) ในสาขาในเร็ว ๆ นี้
              ข้อแตกต่างของกลุ่มวิชาในการเรียนคือ นักศึกษาต้องเลือกรายวิชารวม 6
              รายวิชา (18 หน่วยกิต) จากกลุ่มวิชาใดกลุ่มวิชาหนึ่ง
              โดยต้องเลือกกลุ่มวิชากลุ่มนั้นตลอดหลักสูตร ดังนี้
              <br />
              1.กลุ่มวิชาวิทยาการข้อมูล (Data Science) <br />
              1145 200 การทำคลังข้อมูล(Data Warehousing) 3(2-2-5) <br />
              1145 201 การค้นคืนสารสนเทศ (Information Retrieval) 3(2-2-5) <br />
              1145 202 การประมวลผลภาษาธรรมชาติ(Natural Language Processing)
              3(2-2-5) <br />
              1145 203 ระบบสนับสนุนการตัดสินใจ (Decision Support Systems)
              3(2-2-5) <br />
              1145 204 ปัญญาประดิษฐ์ (Artificial Intelligence) 3(2-2-5) <br />
              1145 205 การทำเหมืองข้อมูล (Data Mining) 3(2-2-5) <br />
              1145 206 การวิเคราะห์ข้อมูลภาพ (Image Analytics) 3(2-2-5) <br />
              1145 207 การรู้จำรูปแบบ (Pattern Recognition) 3(2-2-5) <br />
              1145 208 การเรียนรู้เชิงลึก (Deep Learning) 3(2-2-5) <br />
              1145 209 หัวข้อที่น่าสนใจในวิทยาการข้อมูล (Selected Topics in Data
              Science) 3(2-2-5) <br />
              1145 210 การวิเคราะห์ข้อมูลขนาดใหญ่ (Big Data Analytics) 3(2-2-5)
              <br />
              1145 211 การวิเคราะห์ข้อมูลทางการตลาด (Marketing Data Analytics)
              3(2-2-5) <br />
              2.กลุ่มวิชานวัตกรรมซอฟต์แวร์ (Software Innovation) <br />
              1145 212 การออกแบบซอฟต์แวร์และรูปแบบ (Software Design and Pattern)
              3(2-2-5) <br />
              1145 213 การทดสอบซอฟต์แวร์และการประกันคุณภาพ (Software Testing and
              Quality Assurance) 3(2-2-5) <br />
              1145 214 โซลูชันซอฟต์แวร์เพื่อผู้ประกอบการ (Software Solutions for
              Entrepreneurs) 3(1-4-4) <br />
              1145 215 วิศวกรรมความต้องการ (Requirements Engineering) 3(2-2-5)
              <br />
              1145 216 การพัฒนาและประยุกต์ใช้นวัตกรรมซอฟต์แวร์ (Software
              Innovation Development and Application) 3(2-2-5) <br />
              1145 217 การวัดซอฟต์แวร์ (Software Metrics) 3(2-2-5) <br />
              1145 218 หัวข้อที่น่าสนใจในนวัตกรรมซอฟต์แวร์ (Selected Topics in
              Software Innovation) 3(1-4-4) <br />
              1145 219 การเขียนโปรแกรมภาษาซีชาร์ป (C# Programming) 3(2-2-5)
              <br />
              1145 220 การเขียนโปรแกรมภาษาจาวา (Java Programming) 3(2-2-5)
              <br />
              1145 221 การเขียนโปรแกรมภาษาไพธอน (Python Programming) 3(2-2-5)
              <br />
              1145 222 หัวข้อที่น่าสนใจในภาษาโปรแกรม (Selected Topics in
              Programming Language) 3(2-2-5) <br />
              1146 212 อินเทอร์เน็ตของสรรพสิ่ง (Internet of Things) 3(1-4-4)<br />
            </p>
          </div>
        </v-col>
        <v-col cols="11">
          <hr />
          <p class="mt-4">โปรดเลือกเพียง 1 กลุ่มวิชา</p>
          <v-radio-group v-model="subject" column>
            <v-radio
              label="กลุ่มวิชาวิทยาการข้อมูล (Data Science)"
              value="DataScience"
            ></v-radio>
            <v-radio
              label="กลุ่มวิชานวัตกรรมซอฟต์แวร์ (Software Innovation)"
              value="SoftwareInnovation"
            ></v-radio>
          </v-radio-group>
        </v-col>
        <v-col cols="11">
          <hr />
          <p class="mt-4">
            การเลือกแขนงของนักศึกษามีผลต่อการลงทะเบียนซึ่งการ
            ลงทะเบียนรายวิชาผิดแขนงอาจจะส่งผลให้นักศึกษาจบช้าไม่ เป็นตามแผน
            ***เนื่องจากนักศึกษาต้องเลือกรายวิชารวม 6 ราย วิชา (18 หน่วยกิต)
            จากกลุ่มวิชาใดกลุ่มวิชาหนึ่ง โดยต้องเลือก
            กลุ่มวิชากลุ่มนั้นตลอดหลักสูตร***
          </p>
          <v-radio-group v-model="accept" column>
            <v-radio label="ยอมรับ" value="Yes"></v-radio>
          </v-radio-group>
          <v-btn
            depressed
            color="second"
            dark
            class="w-100 mt-5 my-btn"
            @click="submit"
            >บันทึกแบบสำรวจ</v-btn
          >
          <v-btn
            depressed
            color="third"
            dark
            class="w-100 mt-5 my-btn"
            @click="back"
            >ย้อนกลับ</v-btn
          >
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      subject: null,
      accept: null,
    };
  },
  methods: {
    back() {
      this.$router.push("/teacher/survey/create");
    },
  },
};
</script>
