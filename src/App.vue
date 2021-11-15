<template>
  <div>
    <v-btn color="red">12</v-btn>
    <grid-manager :option="gridOption" ref="grid"></grid-manager>
  </div>
</template>

<script>
import GridManager from 'gridmanager-vue'
import 'gridmanager-vue/css/gm-vue.css'

let data = require('./assets/json/data.json')

export default {
  name: 'App',
  components: {
    GridManager
  },
  computed: {
    gridOption() {
      let that = this
      return {
        gridManagerName: 'UserExcel',
        ajaxData: data,
        query: that.form,
        height: '100%',
        supportDrag: true,
        useCellFocus: true,
        checkboxConfig: {
          fixed: 'left'
        },
        autoOrderConfig: {
          width: 50,
          fixed: 'left'
        },
        supportMoveRow: true,
        moveRowConfig: {
          key: "priority",
          useSingleMode: true,
          fixed: "left"
        },
        supportAjaxPage: true,
        totalsKey: 'total',
        currentPageKey: 'from',
        pageSizeKey: 'to',
        columnData: [
          {
            key: 'name',
            text: '1',
            width: '200px',
            fixed: 'left'
          },
          {
            key: 'current_addr',
            text: '2',
            width: '400px'
          },
          {
            key: 'owner_relation',
            text: '3',
            width: '100px'
          },
          {
            key: 'id_card',
            text: '4',
            width: '180px'
          },
          {
            key: 'gender',
            text: '5',
            width: '50px'
          },
          {
            key: 'nation',
            text: '6',
            width: '80px'
          },
          {
            key: 'tel',
            text: '7',
            width: '120px'
          },
          {
            key: 'investigate_addr',
            text: '8',
            width: '400px'
          },
          {
            key: 'account_addr',
            text: '9',
            width: '400px'
          },
          {
            key: 'enter_time',
            text: '10',
            width: '150px'
          },
          {
            key: 'leave_ac_addr_time',
            text: '11',
            width: '150px'
          },
          {
            key: 'leave_ac_addr_reason',
            text: '12',
            width: '400px'
          },
          {
            key: 'created_at',
            text: '13',
            width: '150px'
          },
          {
            key: 'action',
            text: '操作',
            width: '150px',
            fixed: 'right',
            template: () => {
              return `<v-btn x-small color="primary">编辑</v-btn>
                      <v-btn x-small color="error">删除</v-btn>`;
            }
          }
        ]
      }
    }
  }
};
</script>
