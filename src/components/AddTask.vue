<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label>Task</label>
      <input type="text" v-model="text" name="text" placeholder="Add Task" />
    </div>
    <div class="form-control">
      <label>Day & Time</label>
      <input
        type="text"
        v-model="day"
        name="day"
        placeholder="Add Day & Time"
      />
    </div>
    <div class="form-control form-control-check">
      <label>Add Reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder" />
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
    color: String,
  },
  data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if (!this.text) {
        alert("Please add a task");
        return;
      }

      const newTask = {
        id: Math.floor(Math.random() * 10000),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };
      this.$emit("add-task", newTask);

      this.text = "";
      this.day = "";
      this.reminder = false;
    },
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
  font-size: 16px;
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
  height: 18px;
}
.form-control-check input:checked {
  background-color: #ffa309;
}
</style>