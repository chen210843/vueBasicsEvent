<template>
  <ul>
    <!-- <Person
      v-for="(item, index) in personals"
      :key="index"
      :id="index"
      :name="item.name"
      :level="item.level"
      :major="item.major"
      :hobby="item.hobby"
      :gender="item.gender"
      @delete="remove"
      @edit="update"
    /> -->
    
    <div v-for="(item, index) in personals"
      :key="index"
      :id="index"
      :name="item.name"
      :level="item.level"
      :major="item.major"
      :hobby="item.hobby"
      :gender="item.gender">
      <img src="https://cdn-icons-png.flaticon.com/128/4521/4521022.png">
        <li>-------------------------------------------</li>
        <h3>id:{{index}}</h3>
      <h5>ชื่อ : 
        {{item.name}}</h5>
      <h5>ปัจจุบันศึกษาอยู่ชั้นปี: 
        {{item.level}}</h5>
      <h5>สาขา : 
        {{item.major}}</h5>
      <h5>เพศ :
        {{item.gender}}</h5>
      <button @click="editForm(index)">แก้ไข</button>
      <button @click="deleteForm(index)">ลบ</button>
       <hr>
      </div>
    </ul>
</template>

<script>
// import Person from "./Person.vue";

export default {
  name: "ListData",
  components: {
    // Person,
  },
  props: ["personals"],
  methods: {
    editForm(index) {
     this.$emit("editpersonal",index)

    },
    deleteForm(index) {
      this.$emit("deletepersonal",index)

    },
  },
};
</script>

<style scped>
ul {
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}
img{
    width: 100px;
    height: 100px;
}
</style>
