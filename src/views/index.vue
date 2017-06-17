<template>
<div>
    <div class="tab-tt">
      订单趋势
    </div>
    <ul class="tab-select">
        <li >
         <label><span>CID</span><Input  style="width:130px"></Input></label>
         <label><span>订单状态</span>
 <Select v-model="model4" size="large" style="width:270px">
  <Option v-for="item in state" :value="item.value" :key="item">{{ item.label }}</Option>   
    </Select>
         </label>
        </li>
        <li class="margin-bottom0 clearfix">
          <label class="date-bg ">
          <span class="date-ex">订单生成时间</span>
            <Date-picker type="date" placeholder="选择日期" style="width:130px"></Date-picker>
         </label>
         <label class="date-bg">
          <span class="date-ex">套餐启动时间</span>
            <Date-picker type="date" placeholder="选择日期" style="width:130px"></Date-picker>
         </label>
           <Button type="ghost" class="select-btn">搜索</Button>
          <Button type="ghost" class="select-btn">取消</Button>
           <Button type="ghost" class="export">导出</Button>
        </li>
    </ul>
    <!--  tab-select end -->
  <div class="table-bg">
  <Table border :columns="columns4" :data="data1"></Table>
  <div class="page-bg">
  <Page :total="100" show-sizer></Page>
  </div>
  </div>

<!--   table-bg end -->
</div>
</template>

<style scoped>
    .input-item{border:1px solid #efefef;height:50px; margin-left:2px;}
    .tab-tt{
        height:60px;
        line-height:60px;
        text-indent:25px;
        border-bottom:1px solid #efefef;
        width:100%;
    }
    .tab-select{padding:30px 0px 30px 20px;
    }
    .tab-select li{ margin-bottom:15px; }
    .tab-select li label{ margin-right:25px; }
    .tab-select li span{display:inline-block;width:84px; text-align:right; margin-right:7px;}
    .margin-bottom0{ margin-bottom:0px!important; }
    .ivu-date-picker {
    line-height: normal;
    float: left;}
   .date-ex{ float:left;display:block;height:32px;line-height:32px; }
   .date-bg{margin-right:33px!important; float:left;}
   .export{ float:right; }
   .table-bg{width:100%;padding:0 0 0 20px; }
   .button{ margin-right:20px; }
   .select-btn{ margin-right:25px; }
   .page-bg{margin-top:30px; float:right;}
</style>

<script>
    export default {
       data () {
            return {
                state: [
                    {
                     
                        label: '待支付'
                    },
                    {
                 
                        label: '未激活'
                    },
                    {
                        label: '使用中'
                    },
                    {
                        label: '激活失败'
                    },
                    {
                        label: '已使用'
                    },
                    {
                        label: '退款中'
                    },
                    {
                        label: '已退款'
                    }
                ],
                columns4: [
                    {
                        type: 'selection',
                        width: 60,
                        align: 'center',
                    },
                    {
                        title: 'CID',
                        key: 'name'
                    },
                    {
                        title: 'IMSI',
                        key: 'age'
                    },
                    {
                        title: '订单ID',
                        key: 'address'
                    },
                    {   width: 130,
                        title: '订单生成时间',
                        key: 'address'
                    },
                    {
                        title: '套餐名称',
                        key: 'address'
                    },
                    {
                        title: '套餐启动时间(生效时间)',
                        width: 130,
                        align: 'center',
                        key: 'address'
                    },
                    {
                        title: '订单状态',
                        key: 'address'
                    },
                    {
                        title: '订单金额',
                        key: 'address'
                    },
                     {
                        title: '操作',
                        key: 'address'
                    }
                ],
                data1: [
                    {
                        name: '王小明',
                        age: 18,
                        address: '北京市朝阳区芍药居'
                    },
                    {
                        name: '张小刚',
                        age: 25,
                        address: '北京市海淀区西二旗'
                    },
                    {
                        name: '李小红',
                        age: 30,
                        address: '上海市浦东新区世纪大道'
                    },
                    {
                        name: '周小伟',
                        age: 26,
                        address: '深圳市南山区深南大道'
                    }
                ]
            }
        }  

    };
</script>