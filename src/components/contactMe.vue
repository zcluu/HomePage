<script>
import {defineComponent} from 'vue'
import BaseComponent from "@/components/baseComponent.vue";

export default defineComponent({
    name: "contactMe",
    components: {BaseComponent},
    data() {
        const validateEmail = (rule, value, callback) => {
            if (value === '') {
                callback(new Error('Please input the email'))
            } else {
                if (!this.form.email.match(/^\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$/)) {
                    callback(new Error('Please input valid email'))
                } else
                    callback()
            }
        }
        const validatePhone = (rule, value, callback) => {
            if (value === '') {
                callback(new Error('Please input the phone number'))
            } else {
                if (!this.form.phone.match(/^(13[0-9]|14[01456879]|15[0-35-9]|16[2567]|17[0-8]|18[0-9]|19[0-35-9])\d{8}$/)) {
                    callback(new Error('Please input valid phone number'))
                } else
                    callback()
            }
        }
        const rules = {
            email: [{validator: validateEmail, trigger: 'blur', required: true}],
            phone: [{validator: validatePhone, trigger: 'blur', required: true}],
            message: [{required: true, trigger: 'blur'}],
        }
        return {
            form: {email: '', phone: '', message: ''},
            rules: rules
        }
    },
    methods: {}
})
</script>

<template>
    <base-component
            sub_title="CONTACT"
            main_title="CONTACT ME"
            id="contact"
            :is-white="true"
    >
        <template #mainBox>
            <el-form label-position="top"
                     ref="form"
                     :model="form"
                     :rules="rules"
            >
                <el-form-item label="Your Email:" prop="email">
                    <el-input v-model="form.email"></el-input>
                </el-form-item>
                <el-form-item label="Your PhoneNum:" prop="phone">
                    <el-input v-model="form.phone"></el-input>
                </el-form-item>
                <el-form-item label="Message:" prop="message">
                    <el-input v-model="form.message" type="textarea" rows="5"></el-input>
                </el-form-item>
                <el-row>
                    <el-col :span="12">
                        <el-button type="success" plain>Submit</el-button>
                    </el-col>
                    <el-col :span="12">
                        <el-link href="http://wpa.qq.com/msgrd?v=3&uin=1256234567&site=qq&menu=yes"
                                 style="float:right;"
                        >
                            <img border="0" src="http://wpa.qq.com/pa?p=2:1256234567:41" alt="点击这里给我发消息"
                                 title="点击这里给我发消息">
                        </el-link>
                    </el-col>
                </el-row>
            </el-form>
        </template>
    </base-component>
</template>

<style scoped lang="less">

</style>