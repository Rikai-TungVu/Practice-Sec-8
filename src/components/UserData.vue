<template>
    <form @submit.prevent="submitData">
        <div>
            <label>UserName</label>
            <input type="text" v-model="enteredUsername">
        </div>
        <div>
            <label>Age</label>
            <input type="text" v-model="enteredAge">
        </div>
        <div>
            <button>Add User</button>
        </div>
    </form>
</template>
  
<script>
    export default {
        emits:['user-data'],
        data () {
            return {
                enteredUsername:'',
                enteredAge:''
            };
        },
        methods: {
            submitData () {
                this.$emit(
                    'user-data',
                    this.enteredUsername,
                    this.enteredAge
                    )
            }
        }
    };
</script>