<template>
  <div class="pro-form-demo-container">
    <el-card :body-style="{  background: '#B3C0D1' }">
      <div slot="header">普通用法</div>
      <pro-form
        :fields="fields1"
        label-width="100px"
        @submit="onSubmit"
      />
    </el-card>
  </div>
</template>

<script>
  export default {
    name: "FormPage",
    data() {
      return {
        fields1: [
          {
            key: 'name',
            title: '用户名',
            isRequired: true
          },
          {
            key: 'publishTime',
            title: '发布时间',
            type: 'datetime',
            isRequired: true
          },
          {
            key: 'activeTime',
            title: '活动时间',
            type: 'datetime',
            props: {
              type: 'datetimerange'
            }
          }
        ]
      }
    },
    methods: {
      onSubmit(form, valid) {
        this.$message.info(`校验结果：${valid} 表单数据：` + JSON.stringify(form))
      }
    }
  }
</script>

<style lang="scss">
  .pro-search-demo-container {
    .el-card {
      margin-bottom: 18px;
    }
  }
</style>
