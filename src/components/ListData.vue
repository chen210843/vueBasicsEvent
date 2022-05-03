<template>
  <ul>
    <Person
      v-for="(item,index) in personals"
      :key="index"
      :name="item.name"
      :level="item.level"
      :major="item.major"
      :hobby="item.hobby"
      :gender="item.gender"
    />
  </ul>
</template>

<script>
import Person from "./Person.vue";

export default {
  name: "ListData",
  components: {
    Person,
  },
  props:["personals"]
};
</script >

<style scped>
ul{
    list-style: none;
    margin: 1rem 0 ;
    padding: 0;

}
</style>