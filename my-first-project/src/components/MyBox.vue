<template>
    <div class="box">{{ name }} - {{ age }}
        <span :class="['status', status]">{{ status }}</span>
    </div>
    
</template>

<script>

export default {
    name:'MyBox',
    props: {
        name: {
            type: String,
            default: 'N/A'
        },
        age: {
            type: Number,
            required: true
        },
        status: {
            type: String,
            validator: value => ['active', 'inactive'].includes(value),
            default: 'active'
        }
    }
}

</script>

<style>

.active {
    background-color: green;
    padding: 0 5px;
}

.inactive {
    background-color: grey;
    padding: 0 5px;
}

.box {
  background-color: purple;
  color: white;
  width: auto;
  height: 30px;
  padding: 0 10px;
  border-radius: 4px;
  gap: 10px;

  display: flex;
  align-items: center;
  justify-content: center;

  &:hover {
    background-color: red;
  }
}
</style>