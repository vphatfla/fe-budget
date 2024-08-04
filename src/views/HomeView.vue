<template>
  <div class="col-12 h-100 container d-flex align-items-center">
    <div class="row col-12 d-flex align-items-center">
      <!-- Your page content goes here -->
      <div class="col col-md-9">
        <h1>Welcome to Spending Tracking</h1>
      </div>
      <div class="col col-md-3">
        <div class="row">
          <div class="col">
            <RouterLink class="btn btn-primary" to="/login">Login</RouterLink>
            <!-- <button>Login</button> -->
          </div>
          <div class="col">
            <!-- <button>Sign Up</button> -->
            <RouterLink class="btn btn-primary" to="/signup">Sign Up</RouterLink>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    loginButtonHandler() {}
  }
}
</script>
