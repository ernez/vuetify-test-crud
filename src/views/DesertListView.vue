<template lang="html">

  <crud-component
        crud-form-title="Deserts"
        :headers="headers"
        :item-formats="desertFormats"
        :items="dessertsData"
        sort-by="calories"
        table-class="elevation-1"
        :edited-item-prop="editedItem"
        :default-item-prop="defaultItem"
    />

</template>

<script lang="js">

import CrudComponent from "@/components/CrudComponent";

export default {
  name: 'desert-list-view',
  components: {CrudComponent},
  props: [],
  mounted() {

  },
  data: () => ({
    dialog: false,
    dialogDelete: false,
    headers: [
      {
        text: 'Dessert (100g serving)',
        align: 'start',
        sortable: false,
        value: 'name',
      },
      {text: 'Calories', value: 'calories'},
      {text: 'Fat (g)', value: 'fat'},
      {text: 'Carbs (g)', value: 'carbs'},
      {text: 'Protein (g)', value: 'protein'},
      {text: 'Actions', value: 'actions', sortable: false},
    ],
    dessertsData: [],
    desertFormats: [],
    editedIndex: -1,
    editedItem: {
      name: '',
      calories: 0,
      fat: 0,
      carbs: 0,
      protein: 0,
    },
    defaultItem: {
      name: '',
      calories: 0,
      fat: 0,
      carbs: 0,
      protein: 0,
    }
  }),
  created() {
    this.initialize()
  },

  methods: {
    editedItemOnChildEvent(item) {
      this.editedItem = item
    },
    initialize() {
      this.desertFormats = [
        {
          model: 'name',
          label: 'Dessert name',
          cols: '12',
          sm: '6',
          md: '4'
        },
        {
          model: 'calories',
          label: 'Calories',
          cols: '12',
          sm: '6',
          md: '4'
        },
        {
          model: 'fat',
          label: 'Fat (g)',
          cols: '12',
          sm: '6',
          md: '4'
        },
        {
          model: 'carbs',
          label: 'Carbs (g)',
          cols: '12',
          sm: '6',
          md: '4'
        },
        {
          model: 'carbs',
          label: 'Carbs (g)',
          cols: '12',
          sm: '6',
          md: '4'
        },
        {
          model: 'protein',
          label: 'Protein (g)',
          cols: '12',
          sm: '6',
          md: '4'
        }
      ]
      this.dessertsData = [
        {
          name: 'Frozen Yogurt',
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
        },
        {
          name: 'Ice cream sandwich',
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
        },
        {
          name: 'Eclair',
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
        },
        {
          name: 'Cupcake',
          calories: 305,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
        },
        {
          name: 'Gingerbread',
          calories: 356,
          fat: 16.0,
          carbs: 49,
          protein: 3.9,
        },
        {
          name: 'Jelly bean',
          calories: 375,
          fat: 0.0,
          carbs: 94,
          protein: 0.0,
        },
        {
          name: 'Lollipop',
          calories: 392,
          fat: 0.2,
          carbs: 98,
          protein: 0,
        },
        {
          name: 'Honeycomb',
          calories: 408,
          fat: 3.2,
          carbs: 87,
          protein: 6.5,
        },
        {
          name: 'Donut',
          calories: 452,
          fat: 25.0,
          carbs: 51,
          protein: 4.9,
        },
        {
          name: 'KitKat',
          calories: 518,
          fat: 26.0,
          carbs: 65,
          protein: 7,
        },
      ]
    },
  },
}


</script>

<style scoped lang="scss">
.desert-list-view {

}
</style>
