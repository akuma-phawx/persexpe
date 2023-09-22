<script setup lang="ts">
import { Ref, ref } from "vue";

const expenses: Ref<any[]> = ref([
  {
    id: 23423,
    name: "House Rent",
    year: 2023,
    month: "October",
    toBePaid: 1075,
    paid: 0,
    isSettled: false,
  },
  {
    id: 23423,
    name: "Washing Machine & Dryer",
    year: 2023,
    month: "October",
    toBePaid: 75,
    paid: 75,
    isSettled: true,
  },
]);
</script>
<template>
  <div class="page-container bg-primary vh-100 text-white pt-4">
    <i class="bi bi-check-circle-fill"></i>
    <div id="contentContainer" class="mt-4">
      <table
        class="table table-bordered table-lg-responsive text-center rounded"
      >
        <thead>
          <tr>
            <th scope="col"><h4>Expense</h4></th>
            <th scope="col">To Be Paid</th>
            <th scope="col">Paid</th>
            <th scope="col">Settled</th>
            <th scope="col">Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="expense in expenses" :key="expense.id">
            <td>{{ expense.name }}</td>
            <td>{{ expense.toBePaid }}</td>
            <td>{{ expense.paid }}</td>
            <td>
              <svg
                v-if="expense.isSettled"
                xmlns="http://www.w3.org/2000/svg"
                width="16"
                height="16"
                fill="currentColor"
                class="bi bi-check-circle-fill text-success"
                viewBox="0 0 16 16"
              >
                <path
                  d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zm-3.97-3.03a.75.75 0 0 0-1.08.022L7.477 9.417 5.384 7.323a.75.75 0 0 0-1.06 1.06L6.97 11.03a.75.75 0 0 0 1.079-.02l3.992-4.99a.75.75 0 0 0-.01-1.05z"
                />
              </svg>
              <svg
                v-else
                xmlns="http://www.w3.org/2000/svg"
                width="16"
                height="16"
                fill="currentColor"
                class="bi bi-x-circle-fill text-danger"
                viewBox="0 0 16 16"
              >
                <path
                  d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zM5.354 4.646a.5.5 0 1 0-.708.708L7.293 8l-2.647 2.646a.5.5 0 0 0 .708.708L8 8.707l2.646 2.647a.5.5 0 0 0 .708-.708L8.707 8l2.647-2.646a.5.5 0 0 0-.708-.708L8 7.293 5.354 4.646z"
                />
              </svg>
            </td>
            <td><button class="btn btn-outline-primary">PAY</button></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
