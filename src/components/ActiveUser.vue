<template>
    <li>
        <ul>
            <li>
                <h2><strong>UserName:</strong>{{ username }}</h2>
            </li>
            <li>
                <h3><strong>Age:</strong>{{ age }}</h3>
            </li>
        </ul>
        <button @click="deleteUser">Delete User</button>
    </li>
</template>

<script>
    export default {
        props: {
            id: {
                type: String,
                required: true
            },
            username: {
                type: String,
                required: true
            },
            age: {
                type: String,
                required: true
            }
        },
        emits: ['delete'],
        methods: {
            deleteUser () {
                this.$emit('delete', this.id);
            }
        }
    }
</script>