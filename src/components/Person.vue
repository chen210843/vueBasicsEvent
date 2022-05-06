<template>
  <card>
    <template v-slot:card-header>
      <h3>id:{{id}}</h3>
      <h2>ชื่อ:{{ name }}</h2>
    </template>
    <template v-slot:card-content>
       <p>เพศ: {{gender}}</p>
       <p>ชั้นปีที่: {{ level }}</p>
       <p>สาขา: {{major}}</p>
       <p>งานอดิเรก: {{ hobby }}</p>
    </template>
    <template v-slot:card-button>
      <button @click="editForm(id)">แก้ไข</button>
      <button @click="deleteForm(id)">ลบ</button>
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
    id:{
      type:Number
    },
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
  methods:{
    editForm(id){
       this.$emit("edit",id)
              
    },
    deleteForm(id){
      this.$emit("delete",id)
    }
  }

};
</script>

<style >

</style>

