<template>
  <div class="q-pa-md">
    <q-table
      title="Treats"
      :rows="rows"
      :columns="columns"
      row-key="name"
    >
    <template v-slot:body-cell-avatar="props">
      <q-td :props="props">
        <q-img
          :src="props.row.avatar"
        />
      </q-td>
      </template>
      <template v-slot:body-cell-actions="props">
        <q-td :props="props">
          <q-btn icon="mode_edit" @click="onEdit(props.row.id)"/>
          <q-btn icon="delete" @click="onDelete(props.row.id)"/>
        </q-td>
      </template>
    </q-table>
  </div>
</template>


<script setup>
import { ref } from 'vue';
const columns = ref([
  // แก้หัว column
  { name: 'id', align: 'left', label: 'ID', field: 'id', sortable: true },
  { name: 'fname', label: 'left', label: 'fname', field: 'fname', sortable: true},
  { name: 'lname', label: 'left', label: 'lname', field: 'lname', sortable: true},
  { name: 'username', label: 'left', label: 'username', field: 'username', sortable: true},
  { name: 'avatar', label: 'center', label: 'avatar', field: 'avatar'},
  { name: 'actions', align: 'center', label: 'ID', field: 'id', sortable: true }
])
  
const rows = ref([])
const fetchData = () =>{
  fetch("https://www.melivecode.com/api/users")
  .then(res => res.json())
  .then((result)=>{
    rows.value = result;
  })
}
fetchData()
  // ลำดับของตัวแปรต้องตรงกัน
  // {"id":1,"fname":"Karn","lname":"Yong","username":"karn.yong@melivecode.com","avatar":"https://www.melivecode.com/users/1.png"},
  // {"id":2,"fname":"Ivy","lname":"Cal","username":"ivy.cal@melivecode.com","avatar":"https://www.melivecode.com/users/2.png"},
  // {"id":3,"fname":"Walter","lname":"Beau","username":"walter.beau@melivecode.com","avatar":"https://www.melivecode.com/users/3.png"},
  // {"id":4,"fname":"Gayla","lname":"Bertrand","username":"gayla.bertrand@melivecode.com","avatar":"https://www.melivecode.com/users/4.png"},
  // {"id":5,"fname":"Benjamin","lname":"Chaz","username":"benjamin.chaz@melivecode.com","avatar":"https://www.melivecode.com/users/5.png"},
  // {"id":6,"fname":"Delia","lname":"Robin","username":"delia.robin@melivecode.com","avatar":"https://www.melivecode.com/users/6.png"},
  // {"id":7,"fname":"Hector","lname":"Graves","username":"hector.graves@melivecode.com","avatar":"https://www.melivecode.com/users/7.png"},
  // {"id":8,"fname":"Diego","lname":"Greene","username":"diego.greene@melivecode.com","avatar":"https://www.melivecode.com/users/8.png"},
  // {"id":9,"fname":"Izzie","lname":"Mooney","username":"izzie.mooney@melivecode.com","avatar":"https://www.melivecode.com/users/9.png"},
  // {"id":10,"fname":"Romeo","lname":"Garner","username":"romeo.garner@melivecode.com","avatar":"https://www.melivecode.com/users/10.png"} 

</script>

<style>

</style>