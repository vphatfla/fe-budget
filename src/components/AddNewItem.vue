<template>
  <div class="form row w-100 d-flex justify-content-center">
    <div class="row form-group col-md-2">
      <label>Item Name</label>
      <input />
    </div>
    <div class="row form-group col-md-2">
      <label>Type</label>
      <input />
    </div>
    <div class="row form-group col-md-2">
      <label>Amount</label>
      <input />
    </div>
    <div class="row form-group col-md-2">
      <label>Comment</label>
      <input />
    </div>
    <div class="row form-group col-md-2">
      <label>Date</label>
      <input type="date" />
    </div>
    <div class="row form-group col-md-2 d-flex align-items-center">
      <button type="button" class="btn btn-primary mt-3" style="width: 100px; height: 40px">
        Submit
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddNewItem'
}
</script>
