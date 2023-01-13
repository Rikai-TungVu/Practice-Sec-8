<template>
    <section>
        <header>
            <h1>User List</h1>
        </header>
        <user-data @user-data="addUser"></user-data>
        <ul>
            <active-user
            v-for="user in users"
            :key="user.id"
            :id="user.id"
            :username="user.username"
            :age="user.age"
            @delete="deleteUser"
            ></active-user>
        </ul>
    </section>
</template>

<script>
    export default {
        data () {
            return {
                users: [
                    {
                        id: 'manual',
                        username: 'manal12',
                        age: '19'
                    },
                    {
                        id: 'tester',
                        username: 'tester13',
                        age: '20'
                    }
                ]
            };
        },
        methods: {
            addUser(username, age) {
                const newUser = {
                    id: new Date().toISOString(),
                    username: username,
                    age: age
                };
                this.users.push(newUser);
            },
            deleteUser(userID) {
                this.users = this.users.filter(
                    (user) => user.id == userID
                );
            }
        }
    };
</script>