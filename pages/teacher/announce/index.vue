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
            <v-col cols="4" md="auto"> นางสาวพัฒนิกร ไถ้เงิน </v-col>
            <v-col cols="3" md="auto"> 61114440449 </v-col>
            <v-col cols="4">
              <v-dialog v-model="editStudent" persistent max-width="600px">
                <template v-slot:activator="{ on, attrs }">
                  <v-btn icon small v-bind="attrs" v-on="on" color="indigo">
                    <v-icon>mdi-pencil</v-icon>
                  </v-btn>
                </template>
                <v-card>
                  <v-card-title>
                    <span class="text-primary">ข้อมูลนักศึกษา</span>
                  </v-card-title>
                  <v-card-text>
                    <v-container>
                      <v-row>
                        <v-col cols="12">
                          <v-text-field
                            value="นางสาวพัฒนิกร ไถ้เงิน"
                            label="ชื่อ - นามสกุล"
                            required
                          ></v-text-field>
                        </v-col>
                        <v-col cols="12">
                          <v-text-field
                            value="61114440449"
                            label="รหัสนักศึกษา"
                            type="number"
                            required
                          ></v-text-field>
                        </v-col>
                        <v-col cols="12" class="pt-0 pb-0">
                          <v-radio-group v-model="subject">
                            <template v-slot:label>
                              <div>กลุ่มวิชาที่สามารถเลือกเรียนต่อ</div>
                            </template>
                            <v-radio value="DataScience">
                              <template v-slot:label>
                                <div>
                                  กลุ่มวิชาวิทยาการข้อมูล (Data Science)
                                </div>
                              </template>
                            </v-radio>
                            <v-radio value="SoftwareInnovation">
                              <template v-slot:label>
                                <div>
                                  กลุ่มวิชานวัตกรรมซอฟต์แวร์ (Software
                                  Innovation)
                                </div>
                              </template>
                            </v-radio>
                          </v-radio-group>
                        </v-col>
                      </v-row>
                    </v-container>
                  </v-card-text>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn color="error" text @click="editStudent = false">
                      ปิด
                    </v-btn>
                    <v-btn color="indigo" text @click="editStudent = false">
                      บันทึก
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
              <v-dialog v-model="deleteStudent" persistent max-width="290">
                <template v-slot:activator="{ on, attrs }">
                  <v-btn icon small v-bind="attrs" v-on="on" color="error">
                    <v-icon>mdi-delete</v-icon>
                  </v-btn>
                </template>
                <v-card>
                  <v-card-title class="text-primary">
                    ยืนยันการลบ
                  </v-card-title>
                  <v-card-text>คุณแน่ใจหรือว่าต้องการลบรายชื่อนี้?</v-card-text>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn color="indigo" text @click="deleteStudent = false">
                      ยกเลิก
                    </v-btn>
                    <v-btn color="error" text @click="deleteStudent = false">
                      ยืนยัน
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 2 </v-col>
            <v-col cols="4" md="auto"> นายภากร สารีบุตร </v-col>
            <v-col cols="3" md="auto"> 61114440494 </v-col>
            <v-col cols="4">
              <v-btn icon small color="indigo">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-btn icon small color="error">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 3 </v-col>
            <v-col cols="4" md="auto"> นางสาววรรณสกนธ์ โภคสมบูรณ์ </v-col>
            <v-col cols="3" md="auto"> 61114440571 </v-col>
            <v-col cols="4">
              <v-btn icon small color="indigo">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-btn icon small color="error">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="11">
          <hr />
          <p class="mt-4"> กลุ่มวิชา "นวัตกรรมซอฟต์แวร์ (Software Innovation)" </p>
          <v-row class="pt-2 pb-0">
            <v-col cols="1"> 1 </v-col>
            <v-col cols="4" md="auto"> นายกนต์ธร แก้วอร่าม </v-col>
            <v-col cols="3" md="auto"> 61114440018 </v-col>
            <v-col cols="4">
              <v-btn icon small color="indigo">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-btn icon small color="error">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 2 </v-col>
            <v-col cols="4" md="auto"> นายอนุชา สุภาวงศ์ </v-col>
            <v-col cols="3" md="auto"> 61114440830 </v-col>
            <v-col cols="4">
              <v-btn icon small color="indigo">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-btn icon small color="error">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 3 </v-col>
            <v-col cols="4" md="auto"> นายภัทรพล ผิวเรือง </v-col>
            <v-col cols="3" md="auto"> 61114440472 </v-col>
            <v-col cols="4">
              <v-btn icon small color="indigo">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-btn icon small color="error">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="11">
          <hr />
          <p class="mt-4"> นักศึกษาที่รอการจัดกลุ่มวิชา </p>
          <v-row class="pt-2 pb-0">
            <v-col cols="1"> 1 </v-col>
            <v-col cols="4" md="auto"> นายกนต์ธร แก้วอร่าม </v-col>
            <v-col cols="3" md="auto"> 61114440018 </v-col>
            <v-col cols="4">
              <v-btn icon small color="indigo">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-btn icon small color="error">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 2 </v-col>
            <v-col cols="4" md="auto"> นายอนุชา สุภาวงศ์ </v-col>
            <v-col cols="3" md="auto"> 61114440830 </v-col>
            <v-col cols="4">
              <v-btn icon small color="indigo">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-btn icon small color="error">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="1"> 3 </v-col>
            <v-col cols="4" md="auto"> นายภัทรพล ผิวเรือง </v-col>
            <v-col cols="3" md="auto"> 61114440472 </v-col>
            <v-col cols="4">
              <v-btn icon small color="indigo">
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
              <v-btn icon small color="error">
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
