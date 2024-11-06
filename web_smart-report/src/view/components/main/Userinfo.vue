<template>
    <div id="app">
        <el-table :data="tableData" border style="width: 100%">
            <el-table-column fixed prop="id" label="ID" width="180">
            </el-table-column>
            <el-table-column prop="name" label="创建人" width="180">
            </el-table-column>
            <el-table-column prop="operation" label="操作名称" width="180">
            </el-table-column>
            <el-table-column prop="time" label="操作时间" width="180">
            </el-table-column>
            <el-table-column prop="address" label="用户操作设备IPv4地址" width="180">
            </el-table-column>
            <el-table-column label="操作" width="100">
                <template fixed slot-scope="scope">
                    <el-button @click="handleClick(scope.row)" type="text" size="small">分配权限</el-button>
                </template>
            </el-table-column>
        </el-table>
       

        <el-pagination  fixed="bottom" background layout="prev, pager, next" :total="1000">
        </el-pagination>
    </div>
</template>

<script>
//引入api的接口文件
// import { userRegister } from '@api/user/list';
 
export default {
   name: 'userlist',
    methods: {
        
        submit(){
          this.$axios.post('/api/user/list', this.userFromData).then(res => {
              console.log(res);
          })
        }
    },
   
    data() {
        return {
          userlistData:{
            id:"",
            name:"",
            operation:"",
            time:"",
            address:""
          },

          }
        }
      }
    


</script>
