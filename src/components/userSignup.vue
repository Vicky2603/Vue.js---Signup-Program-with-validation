<template>
    <div>
        <h1>Welcome to Student Registration Form</h1><br><br>
        <p v-if="user.error.length">
            <b>Please fill correctly</b>
            <ul>
                <li v-for="e in user.error" v-bind:key="e.id">
                    {{e}}
                </li>
            </ul>
        </p>
        
            <input class="inputting" v-model="user.name" type="text" placeholder="Enter Name" /><br><br>
            <input class="inputting" v-model="user.email" type="email" placeholder="Enter Email" /><br><br>
            <input class="inputting" v-model="user.Iname" type="text" placeholder="Institute Name" /><br><br>
            <input class="inputting" v-model="user.regd" type="text" placeholder="Registration Number" /><br><br>
            <input class="inputting" v-model="user.pswd" type="password" placeholder="Password" /><br><br>
            <input class="inputting" v-model="user.Cpswd" type="password" placeholder="Confirm Password" /><br><br>
            <p>Select Gender</p>
            <input type="radio" value="Male" id="Male"  v-model="user.gender"/>
            <label for="Male">Male</label><br><br>
            <input type="radio" value="Female" id="Female" v-model="user.gender"/>
            <label for="Female">Female</label><br><br>
            <Button v-on:click="validations">Submit</Button>
    </div>    
</template>

<script>
export default {
    name:"userSignup",
    data() {
        return {
            user: {
                error:[],
                name:null,
                email:null,
                Iname:null,
                regd:null,
                pswd:null,
                Cpswd:null,
                gender:null,
            }
        }
    },
    methods: {
        validations(e) {
            //console.log("No Errors");

            this.error=[];
            if(this.user.name && this.user.email && this.user.Iname && this.user.regd && this.user.pswd && this.user.Cpswd && this.user.gender)
            {
                console.warn("Signup Successful");
            }
            if(!this.user.name)
            {
                this.user.error.push("Name is required");
            }
            if(!this.user.email)
            {
                this.user.error.push("Email is required");
            }
            if(!this.user.Iname)
            {
                this.user.error.push("Institue Name is required");
            }
            if(!this.user.regd)
            {
                this.user.error.push("Registration Number is required");
            }
            if(!this.user.pswd)
            {
                this.user.error.push("Password is required");
            }
            if(!this.user.Cpswd)
            {
                this.user.error.push("Confirm Password is required");
            }
            if(!this.user.gender)
            {
                this.user.error.push("Please select Gender!");
            }
            //console.warn("Signup Successful", this.error);
            e.preventDefault(); 
        }
    }
}
</script>


<style scoped>
.inputting {
    border-block-start-width: 2px;   
}
</style>