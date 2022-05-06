<template>
  <header>
    <h1>ข้อมูลส่วนตัว</h1>
  </header>
  <FormComponent @save="insertpersonal" />
  <section class="personal-content" v-if="personals.length > 0">
    <h3>ข้อมูล</h3>
    <ListData
      :personals="personals"
      @editpersonal="updatepersonal"
      @deletepersonal="deletedata"
    />

  </section>
</template>

<script>
import FormComponent from "./components/FormComponent.vue";
import ListData from "./components/ListData.vue";
export default {
  name: "App",
  components: {
    ListData,
    FormComponent,
  },
  data() {
    return {
      personals:[],
      // newpersonal:[]
    };
  },
  methods: {
    insertpersonal(data) {
      this.personals.push(data);
      // this.newpersonal.push(data);
    },
    updatepersonal(index){
      this.personals[index]
      console.log(this.personals[index])
      this.personals = this.personals[index]
       
    },
    deletedata(index) {
      this.personals.splice(this.personals.indexOf(index), 1);
    },
  },
};
</script>

<style scoped>
* {
  box-sizing: border-box;
}
header {
  text-align: center;
}
.personal-content {
  box-shadow: 0 2px 8ox rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}
h1 {
  color: black;
}
</style>
