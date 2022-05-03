<template>
<header>
  <h1>ข้อมูลส่วนตัว</h1> 
  
  </header>
  <FormComponent @save="insertpersonal"/>
  <section  class="personal-content" v-if="personals.length>0">
    <h2>ข้อมูล</h2>
    <ListData :personals="personals"/>
    <button>แก้ไขข้อมูล</button>
  </section>
</template>

<script>
import FormComponent from './components/FormComponent.vue';
import ListData from "./components/ListData.vue";
export default {
  name: "App",
  components: {
    ListData,
    FormComponent,
 
  },
  data(){
    return{
      personals:[]
    }
  },
  methods:{
    insertpersonal(data){
      this.personals.push(data);
    }
  }
  
};
</script>

<style scoped>
*{
  box-sizing: border-box;
}
header{
  text-align: center;
}
.personal-content{
  box-shadow: 0 2px 8ox rgba(0,0,0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}
h1{
  color: black;
}
</style>