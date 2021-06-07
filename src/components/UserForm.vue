<template>
    <a-table :columns="columns" :data-source="data">
        <template #customTitle>
            <span>
                <smile-outlined />
                Name
            </span>
        </template>
        <template #name="{ text: fuck }">
            <a>{{ fuck }}</a>
        </template>
        <template #tags="{ text: tags }">
            <span>
                <a-tag v-for="tag in tags" :key="tag" :color="tag === 'loser' ? 'volcano' : tag.length > 5 ? 'geekblue' : 'green'">
                    {{ tag.toUpperCase() }}
                </a-tag>
            </span>
        </template>
        <template #action="{ record }">
            <span>
                <a data-record="123" @click="onDelete(record,$event)">删除</a>
                <a-divider type="vertical" />
                <a @click="handleAdd">编辑</a>
            </span>
        </template>
    </a-table>
    <a-button class="editable-add-btn" @click="handleAdd" style="margin-bottom: 8px">Add</a-button>
</template>
<script>
import { SmileOutlined } from '@ant-design/icons-vue';
import { defineComponent } from 'vue';

export default defineComponent({
    // setup() {
    //     const columns = [
    //         // {
    //         //         dataIndex: 'name',
    //         //         key: 'name',
    //         //         slots: {
    //         //             title: 'customTitle',
    //         //             customRender: 'name',
    //         //         },
    //         //     },
    //         {
    //             // title: 'Name',
    //             dataIndex: 'name',
    //             key: 'name',
    //             slots: {
    //                 title: 'customTitle',
    //                 customRender: 'name'
    //             }
    //         },
    //         {
    //             title: 'Age',
    //             dataIndex: 'age',
    //             key: 'age',
    //         },
    //         {
    //             title: 'Address',
    //             dataIndex: 'address',
    //             key: 'address',
    //         },
    //         {
    //             title: 'Tags',
    //             key: 'tags',
    //             dataIndex: 'tags',
    //             slots: {
    //                 customRender: 'tags',
    //             },
    //         },
    //         {
    //             title: 'Action',
    //             key: 'action',
    //             slots: {
    //                 customRender: 'action',
    //             },
    //         },
    //     ];
    //     const data = ref([{
    //             id: 0,
    //             key: '1',
    //             name: 'John Brown',
    //             age: 32,
    //             address: 'New York No. 1 Lake Park',
    //             tags: ['nice', 'developer'],
    //         },
    //         {
    //             id: 1,
    //             key: '2',
    //             name: 'Jim Green',
    //             age: 42,
    //             address: 'London No. 1 Lake Park',
    //             tags: ['loser'],
    //         },
    //         {
    //             id: 2,
    //             key: '3',
    //             name: 'Joe Black',
    //             age: 32,
    //             address: 'Sidney No. 1 Lake Park',
    //             tags: ['cool', 'teacher'],
    //         },
    //     ]);

    //     const count = computed(() => data.value.length + 1);

    //     const onDelete = key => {
    //         console.log("length: ", data.value.length)
    //         console.log("Key: ", key)
    //         data.value = data.value.filter(item => item.key !== key);
    //     };

    //     const handleAdd = () => {
    //         const newData = {
    //             id: `${count.value - 1}`,
    //             key: `${count.value}`,
    //             name: 'Coco',
    //             age: 22,
    //             address: 'Sidney No. 1 Lake Park',
    //             tags: ['sex', 'Fucker'],
    //         };
    //         data.value.push(newData);
    //     };

    //     return {
    //         data,
    //         columns,
    //         count,
    //         onDelete,
    //         handleAdd,
    //     };
    // },

    data(){
        return{
            data: [{
                id: 0,
                key: '1',
                name: 'John Brown',
                age: 32,
                address: 'New York No. 1 Lake Park',
                tags: ['nice', 'developer'],
            },
            {
                id: 1,
                key: '2',
                name: 'Jim Green',
                age: 42,
                address: 'London No. 1 Lake Park',
                tags: ['loser'],
            },
            {
                id: 2,
                key: '3',
                name: 'Joe Black',
                age: 32,
                address: 'Sidney No. 1 Lake Park',
                tags: ['cool', 'teacher'],
            }],

            columns: [{
                // title: 'Name',
                dataIndex: 'name',
                key: 'name',
                slots: {
                    title: 'customTitle',
                    customRender: 'name'
                }
            },
            {
                title: 'Age',
                dataIndex: 'age',
                key: 'age',
            },
            {
                title: 'Address',
                dataIndex: 'address',
                key: 'address',
            },
            {
                title: 'Tags',
                key: 'tags',
                dataIndex: 'tags',
                slots: {
                    customRender: 'tags',
                },
            },
            {
                title: 'Action',
                key: 'action',
                slots: {
                    customRender: 'action',
                },
            }]
        }
    },

    methods:{
        onDelete(record,e){
            console.log(record);
            console.log(e.srcElement.dataset.record);
        },
        handleAdd(){
           
        }
    },

    components: {
        SmileOutlined,
    }
});
</script>