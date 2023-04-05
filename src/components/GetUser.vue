<template>
    <form @submit="onSubmit" class="get-form">
        <div class="form-control">
            <label>User</label>
            <input type="text" v-model="username" name="username" placeholder="Search User" />
        </div>
        <input type="submit" value="View Skills" class="btn btn-block" />
    </form>
</template>

<script>

export default {
    name: 'GetUser',
    data() {
        return {
            username: '',
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()
            if (!this.username) {
                alert('Please type username')
                return
            }
           
            this.$emit('get-skills', this.username)
            this.user = ''
        },
    },
}
</script>

<style scoped>
.get-form {
    margin-bottom: 40px;
}

.form-control {
    margin: 20px 0;
}

.form-control label {
    display: block;
}

.form-control input {
    width: 100%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
}

.form-control-check {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.form-control-check label {
    flex: 1;
}

.form-control-check input {
    flex: 2;
    height: 20px;
}
</style>