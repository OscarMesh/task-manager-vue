<template>
  <form class="add-form">
    <div class="form-control">
      <label>Task</label>
      <input type="text" name="text" placeholder="Add Task" />
    </div>
    <div class="form-control">
      <label>Day & Time</label>
      <input type="text" name="day" placeholder="Add Day & Time" />
    </div>
    <div class="form-control form-control-check">
      <label>Add Reminder</label>
      <input type="checkbox" name="reminder" />
    </div>

    <input
      type="submit"
      value="Save Task"
      :style="{ background: color }"
      class="btn btn-block"
    />
  </form>
</template>


<script>
export default {
  name: "AddTask",

  props: {
    text: String,
    color: String,
  },
};
</script>

<style scoped>
.add-form {
  margin-bottom: 10px;
}

.form-control {
  margin: 10px 0;
}

.form-control label {
  display: block;
}

.form-control input {
  width: 100%;
  margin-top: 10px;
  padding: 3px 7px;
  font-size: 17px;
  height: 54px;
  background: #ffffff;
  border: 1px solid #ffa309;
  border-radius: 5px;
  outline: none;
}

.form-control-check {
  display: flex;
  flex-direction: row;
  align-items: center;
  /* gap: 226px; */
  justify-content: space-between;
}

.form-control-check label {
  flex: 1;
}

.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>