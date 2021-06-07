<template>
    <a-layout class="layout">
        <a-layout-content style="padding: 0 50px">
            <a-breadcrumb style="margin: 16px 0">
                <a-breadcrumb-item>用户信息</a-breadcrumb-item>
            </a-breadcrumb>
            <div :style="{ background: '#fff', padding: '24px', minHeight: '280px' }">
                <UserForm></UserForm>
            </div>
        </a-layout-content>
        <a-layout-footer style="text-align: center">
            ©2021 Created by Yu Zhang
        </a-layout-footer>
    </a-layout>
</template>
<script>
    import UserForm from './UserForm.vue'
    import {
        defineComponent,
        ref
    } from 'vue';
    export default defineComponent({
        setup() {
            return {
                selectedKeys: ref(['2']),
            };
        },
        components: {
            UserForm
        }
    });
</script>
<style>
    .site-layout-content {
        min-height: 280px;
        padding: 24px;
        background: #fff;
    }

    #components-layout-demo-top .logo {
        float: left;
        width: 120px;
        height: 31px;
        margin: 16px 24px 16px 0;
        background: rgba(255, 255, 255, 0.3);
    }

    .ant-row-rtl #components-layout-demo-top .logo {
        float: right;
        margin: 16px 0 16px 24px;
    }

    [data-theme='dark'] .site-layout-content {
        background: #141414;
    }
</style>