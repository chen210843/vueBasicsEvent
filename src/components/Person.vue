<template>
  <card>
    <template v-slot:card-header>
      <h2>ชื่อ:{{ name }}</h2>
    </template>
   
    <template v-slot:card-content>
      <p>เพศ: {{gender}}</p>
       <p>ชั้นปีที่: {{ level }}</p>
       <p>สาขา: {{major}}</p>
       <p>งานอดิเรก: {{ hobby }}</p>
    </template>
  </card>
</template>

<script>
import card from "./card.vue";

export default {
  name: "PersonData",
  components: {
    card,
  },
  props: {
    name: {
      type: String,
      required: true,
    },
    level: {
      type: String,
      required: true,
    },
    major:{
      type:String,
      required:true,
    },
    hobby: {
      type: String,
      required: true,
    },
    gender:{
      type:String
    },
  },

};
</script>

<style >

</style>

