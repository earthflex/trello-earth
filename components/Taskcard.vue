<template>
  <v-card class="mx-auto" max-width="400">
    <v-img
      class="white--text align-end"
      height="200px"
      src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
    >
    </v-img>

    <v-card-subtitle class="pb-0"> 12 เม.ย. 2565</v-card-subtitle>

    <v-card-text class="text--primary">
      <h3>Title</h3>
      <div>
        Lorem Ipsum is simply dummy text of the printing and typesetting
        industry.
      </div>
    </v-card-text>

    <v-card-actions class="justify-end">
      <v-btn color="muted" text>
        <v-icon aria-hidden="false"> mdi-pencil</v-icon> แก้ไข
      </v-btn>

      <v-btn color="red" text>
        <v-icon aria-hidden="false"> mdi-delete</v-icon> ลบ
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {

  data() {
    return {
      items: [
        {
          id: 0,
          title: "Item A",
          list: 1,
        },
        {
          id: 1,
          title: "Item B",
          list: 1,
        },
        {
          id: 2,
          title: "Item C",
          list: 2,
        },
      ],
    };
  },
};
</script>
