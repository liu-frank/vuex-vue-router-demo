<style lang="less" scoped>
    .login-msg {
        padding: 50px;
        text-align: center;
    }
    .msg {
        padding: 50px;
        text-align: center;
        font-size: 20px;
        color: red;
    }
</style>
<template>
    <div>
        <v-header title="首页">
            <router-link slot="right" v-if="user.id" to="/home">{{user.name}}</router-link>
        </v-header>
        <div class="login-msg" v-if="!user.id">
            <router-link to="/login">你还未登录，请先登录</router-link>
        </div>
        <div class="msg" v-if="user.id">
           商户
        </div>
    </div>
</template>
<script>
    import { mapState } from 'vuex'
    export default {
        computed: mapState({ user: state => state.user }),
    }
</script>