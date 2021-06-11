<template>
    <v-container class="grid">
        <v-row>
            <v-col>
                <div class="gridItem">
                    <label for="First Name">First Name: </label>
                    <input v-model="provider.firstName">
                </div>
                <div class="gridItem">
                    <label for="Last Name">Last Name: </label>
                    <input label="Last Name" v-model="provider.lastName">
                </div>
            </v-col>
            <v-col>
                <div class="gridItem">
                    <label for="NPI Number">NPI Number: </label>
                    <input label="NPI Number" v-model="provider.NPINumber">
                </div>
                <div class="gridItem">
                     <label for="address">Business Address: </label>
                    <input label="address" v-model="provider.address">
                </div>
            </v-col>
            <v-col>
                <div class="gridItem">
                    <label for="phone">Telephone Number: </label>
                    <input label="phone" @keyup="formatPhone()" v-model="provider.phoneNumber">
                </div>
                <div class="gridItem">
                     <label for="email">Email Address: </label>
                    <input label="email" v-model="provider.email">
                </div>
            </v-col>
        </v-row>
        <br>
        <button type="submit" @click="checkForm()">Submit</button>
    </v-container>
</template>

<script>
export default {
    data() {
        return {
            provider: {
                firstName: '',
                lastName:'',
                NPINumber: '',
                address:'',
                phoneNumber: '',
                email: '',
            }
        }
    },
    methods: {
        checkForm() {
            if(this.provider.firstName == ''){
                alert("Please enter a first name");
            }
            if(this.provider.lastName == ''){
                alert("Please enter a last name");
            }
            if(this.provider.NPINumber == ''){
                alert("Please enter a NPI number");
            }
            if(this.provider.address == ''){
                alert("Please enter an address");
            }
            if(this.provider.phoneNumber == ''){
                alert("Please enter a telephone number");
            }
            if(this.provider.email == ''){
                alert("Please enter an email");
            }
            if(confirm("Is the information entered correct?\nFirst Name: "+this.provider.firstName+"\nLast Name: "+this.provider.lastName+"\nNPI Number: "+this.provider.NPINumber+"\nBusiness Address: "+this.provider.address+"\nPhone Number: "+this.provider.phoneNumber+"\nEmail Address: "+this.provider.email)){
                alert("Thank you for your information");
                window.location.href = '/ConfirmationPage'
            }
        },
        formatPhone() {
            var cleaned = ('' + this.provider.phoneNumber).replace(/\D/g, '');
            var match = cleaned.match(/^(1|)?(\d{3})(\d{3})(\d{4})$/);
            if (match) {
                var intlCode = (match[1] ? '+1 ' : '');
            this.provider.phoneNumber = [intlCode, '(', match[2], ') ', match[3], '-', match[4]].join('');
  }
  return null;
        }
    },
}
</script>
<style scoped>


.grid-item{
  border:thin gray solid;
  padding:10px;
  width: 30%
}
</style>