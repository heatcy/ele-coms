<script>
export default {
  data() {
    return {
      list: [
        {
          label: '日期', prop: 'date', width: '180'
        },
        {
          label: '名称', prop: 'name', width: '180'
        },
        {
          label: '地址', prop: 'address',
          slot(h, { row }) {
            console.log(row)
            return h('div', {
              style: {
                color: '#3a8ee6'
              }
            }, row.address)
          }
        }
      ],
      data: [{
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1517 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1519 弄'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1516 弄'
      }]
    }
  },
  render(h) {
    return h('div', [
      h('el-table', {
        class: {

        },
        props: {
          data: this.data
        },
        style: {
          width: '100%'
        }
      }, this.list.map(item => {
        return h('el-table-column', {
          props: {
            prop: item.prop,
            label: item.label,
            key: item.prop,
            width: item.width || 'auto'
          },
          scopedSlots: {
            // row,column,$index,store,_self
            default: ({ row, column, $index }) => {
              if (typeof item.slot === 'function') {
                return item.slot(h, { row, column, $index })
              }
              return h('span', row[item.prop])
            }
          }
        })
      }))
    ])
  }
}
</script>
