<template>
  <div class="h-100 container">
    <div class="row col-12 mt-4">
      <div class="col">
        <h4>Hello, {{ this.u_name }}</h4>
        <div class="mb-4"></div>
        <div class="card p-4">
          <TableData :transactionsArr="transactionsArr"></TableData>
          <div class="row d-flex justify-content-center mt-4">
            <button
              class="btn btn-primary"
              style="width: fit-content"
              @click="this.showAddNewItem = !this.showAddNewItem"
            >
              Add New Item
            </button>
          </div>
          <div v-show="showAddNewItem" class="row mt-2">
            <AddNewItem></AddNewItem>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TableData from '../components/TableData.vue'
import { getTransactionsByUserId } from '../util/transactionsUtil.js'
import { getAccountDetails } from '../util/accountUtil.js'
import { useRouter, useRoute } from 'vue-router'
import AddNewItem from '../components/AddNewItem.vue'
export default {
  name: 'Transactions',
  components: { TableData, AddNewItem },
  data() {
    return {
      transactionsArr: [],
      u_name: '',
      showAddNewItem: false
    }
  },
  methods: {
    async fetchTransactions() {
      const route = useRoute()
      const user_id = localStorage.getItem('user_id') || route.query.user_id
      const res = await getTransactionsByUserId(user_id)
      this.fetchUserInformation(user_id)
      this.transactionsArr = res
    },
    /* eslint-disable @typescript-eslint/no-explicit-any */
    async fetchUserInformation(user_id) {
      const res = await getAccountDetails(user_id)
      this.u_name = res.name
    }
  },
  mounted() {
    this.fetchTransactions()
  }
}
</script>
