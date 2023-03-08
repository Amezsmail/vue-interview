<template>
  <div class="container-fluid">
    <form class="formInfo">
    <div class="form-group card col-sm-12">
        <div class="form-group">
            <label for="name"> Name:</label>
            <input type="text" id="name" class="form-control" placeholder="Name" v-model="name" >
        </div >
            <div class="form-group">
                <label for="email"> Email:</label>
                <input type="email" id="email" class="form-control" placeholder="name@example.com" v-model="email">
            </div >
            <div class="form-group">
                <label for="password"> Password:</label>
                <input type="password" id="password" class="form-control" placeholder="Password" v-model="password">
            </div >
            <div class="form-group">
                <label for="password_confirmation"> Confirm password:</label>
                <input type="password" id="password_confirmation" class="form-control" placeholder="Confirm Password" v-model="password_confirmation">
            </div >
            <div class="form-group">
                <label for="gender"> Gender:</label>
                <select id="gender" class="form-control" placeholder="" v-model="gender">
                        <option>None Selected</option>
                        <option>Male</option>
                        <option>Female</option>
                </select>
            </div >
            <div class="form-group">
                <label for="phone"> Phone:</label>
                <input type="text" id="phone" class="form-control" placeholder="(0) 123 456 6789" v-model="phone">
            </div >
            <div class="form-group">
                <label for="passport"> Passport Photo:</label>
                <input type="file" name="" id="passport" class="form-control" placeholder="Passport Photo" @change="onChange">
            </div >
            <div class="form-group">
                <label for="id_card"> ID Photo:</label>
                <input type="file" name="" id="id_card" class="form-control" placeholder="ID Photo" @change="onChange">
            </div >
            <div class="form-group">
                <button label="Submit" id="submit" class="btn btn-primary" @click="showData()">Submit</button>
            </div >
        </div>
    </form>

</div>
</template>
<script>
export default{
  data(){
        return{
            output: '',
            name: '',
            email:'',
            phone:'',
            password:'',
            password_confirmation: '',
            gender:'',
            passport: null,
            id_card: null

        }
    },
    methods: {
    showData (){
        this.output = this.$refs.my_input.value
        console.log(this.output)
    },
        sendData(){
                    
        axios.post("http://192.168.200.95:8080/api/create");
            
     },
     onChange(event){
      passport = console.log(this.passport);
      id_card = console.log(this.id_card);
     }
}
}
</script>


