<template lang="pug">
  v-simple-table(fixed-header='' height='300px')
    template(v-slot:default='')
      thead
        tr
          th.text-left Name
          th.text-left quantity
      tbody
        tr(v-for='item in medicines' :key='item.name')
          td {{ item.name }}
          td {{ item.quantity }}
</template>

<script>
export default {
  data() {
    return {
      medicines: [
        {
          name: "medicine",
          quantity: "5"
        }
      ]
    };
  }
};
</script>