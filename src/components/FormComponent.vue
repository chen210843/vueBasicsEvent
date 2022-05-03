<template>
 <form @submit.prevent="submitForm">
  <div class="form-control"></div>
  <label for="emp-name">ชื่อ-นามสกุล</label>
  <input type="text" v-model.trim="personal.name" required/>
  <div class="form-control"></div>
  <label for="salary">ปัจจุบันศึกษาอยู่ชั้นปี</label>
  <!-- <input type="number" v-model="employee.salary"/> -->
  <select v-model="personal.level">
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
      <option value="4">4</option>
      <option value="5">5</option>
  </select>
  <div class="form-control"></div>
  <label for="emp-name">สาขา</label>
  <input type="text" v-model="personal.major" required />
  <div class="form-control"></div>
  <label for="salary">งานอดิเรก</label>
  <select v-model="personal.hobby">
      <option value="อ่านหนังสือ">อ่านหนังสือ</option>
      <option value="เล่นกีฬา">เล่นกีฬา</option>
      <option value="เล่นเกม">เล่นเกม</option>
      <option value="ดูหนัง">ดูหนัง</option>
  </select>
   <div class="form-control"></div>
  <h2>เพศ</h2>
  <div>
       <input type="radio" value="ชาย" v-model="personal.gender"/>
       <label for="gender-name">ชาย</label>
  </div>
    <div>
       <input type="radio" value="หญิง"  v-model="personal.gender"/>
       <label for="gender-name">หญิง</label>
  </div>
  <div>
      <button>บันทึกข้อมูล</button>
  </div>
 </form>
</template>

<script>
export default {
    name:"FormComponent",
    data(){
        return{
           personal:{
               name:"",
               level:"1",
               major:"",
               hobby:"อ่านหนังสือ",
               gender:"",
               number:5
           } 
        }
    },
    methods:{
        submitForm(){
            const newPersonal={
                name:this.personal.name,
                level:this.personal.level,
                major:this.personal.major,
                hobby:this.personal.hobby,
                gender:this.personal.gender,
                number:this.personal.number,
              

            }
            this.$emit("save",newPersonal);
            this.resetForm();
        },
        resetForm(){
            this.personal.name="";
            this.personal.level="1";
            this.personal.major="";
            this.personal.hobby="อ่านหนังสือ";
            this.personal.gender="";
        }
    }
}
</script>

<style scoped> 
form{
    margin: 2rem auto;
    max-width: 40rem;
    border-radius: 12px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.25);
    padding: 2rem;
    background: #fff;
}
.form-control{
    margin: 00.5rem 0;
}
label{
    font-weight: bold;
}
input,select{
    display: block;
    width: 100%;
    font: inherit;
    margin-top: 0.5rem;
}

input[type="radio"],input[type="checkbox"]{
    display: inline-block;
    width: auto;
    margin-right: 1rem;
}
input[type="radio"]+label,
input[type="checkbox"]+label{
    font-weight: normal;
}
h2{
    font-size: 1rem;
    margin: 0.5rem 0;
}

</style>