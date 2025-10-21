<template>
  <div class="flex items-center justify-center min-h-screen bg-gradient-to-tr from-indigo-50 to-white">
    <div class="bg-white shadow-lg rounded-2xl p-10 text-center">
      <h1 class="text-2xl font-semibold text-gray-700 mb-4">Are you sure you want to log out?</h1>
      <p class="text-gray-500 mb-8">We’ll miss you, come back soon 💫</p>
      <div class="flex justify-center gap-4">
        <button
          @click="logout"
          class="bg-indigo-500 hover:bg-indigo-600 text-white px-6 py-2 rounded-xl transition duration-300"
        >
          Yes, Log Out
        </button>
        <button
          @click="cancel"
          class="border border-indigo-300 text-indigo-600 px-6 py-2 rounded-xl hover:bg-indigo-50 transition duration-300"
        >
          Cancel
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
function logout() {
  console.log('User logged out')
  // redirect logic
}

function cancel() {
  console.log('Logout canceled')
  // go back logic
}
</script>
