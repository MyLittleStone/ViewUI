<template>
  <div>
    <div style="margin: 0 0px">
      <Table
        @on-column-width-resize="handleResize"
        border
        :columns="columns6"
        :data="data5"
        :move="true"
        @on-column-position-changed="handlePosition"
      ></Table>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      columns6: [
        {
          title: "Date",
          key: "date",
          resizable: true,
          width: 180,
        },
        {
          title: "Name",
          key: "name",
          resizable: true,
          width: 180,
        },
        {
          title: "Age",
          key: "age",
          resizable: true,
          width: 180,
        },
        {
          title: "Address",
          key: "address",
        },
      ],
      data5: [
        {
          name: "John Brown",
          age: 18,
          address: "New York No. 1 Lake Park",
          date: "2016-10-03",
        },
        {
          name: "Jim Green",
          age: 24,
          address: "London No. 1 Lake Park",
          date: "2016-10-01",
        },
        {
          name: "Joe Black",
          age: 30,
          address: "Sydney No. 1 Lake Park",
          date: "2016-10-02",
        },
        {
          name: "Jon Snow",
          age: 26,
          address: "Ottawa No. 2 Lake Park",
          date: "2016-10-04",
        },
      ],
    };
  },
  methods: {
    handleResize(width, a, b, c) {
      console.log("changewidth", width, a, b, c);
    },
    handlePosition(from, to, column, event) {
      console.log("handlePosition", from, to);
      let source = this.columns6.splice(from, 1)[0];
      this.columns6.splice(to, 0, source);
    },
  },
};
</script>
