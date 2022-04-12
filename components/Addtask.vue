<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent max-width="600px">
      <template v-slot:activator="{ on, attrs }">
        <v-btn color="" v-bind="attrs" v-on="on">
          <v-icon aria-hidden="false"> mdi-plus </v-icon> เพิ่มสิ่งที่ต้องทำ
        </v-btn>
      </template>
      <v-card>
        <v-card-title>
          <span class="text-h5">เพิ่มสิ่งที่ต้องทำ</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col cols="12">
                <v-text-field
                  label="เพิ่มสิ่งที่ต้องทำ*"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-textarea
                  name="input-7-1"
                  label="รายละเอียด"
                  value=""
                  hint=""
                ></v-textarea>
              </v-col>
              <v-col cols="12">
                <template>
                  <v-file-input multiple label="ไฟล์ภาพประกอบ"></v-file-input>
                </template class="pl-4">
               <v-chip class="mb-2">แสดงผลภาพอัปโหลด:</v-chip>
                  <v-img
                    lazy-src="https://picsum.photos/id/11/10/6"
                    max-height="150"
                    max-width="250"
                    src="https://picsum.photos/id/11/500/300"
                    ></v-img>
              </v-col>
            
              <v-col
                    cols="12"
                    sm="12"
                    md="12"
                    >
                    <v-dialog
                        ref="dialog"
                        v-model="modal"
                        :return-value.sync="date"
                        persistent
                        width="290px"
                    >
                        <template v-slot:activator="{ on, attrs }">
                        <v-text-field
                            v-model="dateRangeText"
                            label="วันเริ่มต้น-สิ้นสุด"
                            prepend-icon="mdi-calendar"
                            readonly
                            v-bind="attrs"
                            v-on="on"
                        ></v-text-field>
                        </template>
                        <v-date-picker
                        v-model="dates"
                        range
                        >
                        <v-spacer></v-spacer>
                        <v-btn
                            text
                            color="primary"
                            @click="modal = false"
                        >
                            ยกเลิก
                        </v-btn>
                        <v-btn
                            text
                            color="primary"
                            @click="$refs.dialog.save(date)"
                        >
                            ยืนยัน
                        </v-btn>
                        </v-date-picker>
                    </v-dialog>
                    </v-col>
            </v-row>
          </v-container>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" text @click="dialog = false">
            ยกเลิก
          </v-btn>
          <v-btn color="blue darken-1" text @click="dialog = false">
            บันทึก
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    dialog: false,
    dates: ['2019-09-10', '2019-09-20'],
  }),
   computed: {
      dateRangeText () {
        return this.dates.join(' ถึง ')
      },
    },
};
</script>
