<template>
  <div class="card ">
    <div :class="[customClass,'rounded-border']">
    <FontAwesomeIcon :icon="icon" />
    </div>
    <div>
    <p class="value">{{ value }}</p>
    <p class="title">{{ title }}</p>
  </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
export default {
  name: 'CardComponent',
  components: {
    FontAwesomeIcon
  },
  props: {
    title: {
      type: String,
      required: true
    },
    value: {
      type: String,
      required: true
    },
    icon: {
      type: Object,
      required: true
    },
    customClass:{
      type:String,
      required:true
    }
  }
}
</script>

<style scoped>
.card{
  padding: 0px 18px;
  background-color: white;
  display:flex;
  align-items: center;
  
  gap:20px;
  grid-column-start:1;
  grid-column-end: 2;
}
.rounded-border{
  padding:10px 13px;
  color:white;
  border-radius: 50%;
}
.value{
  font-size:18px;
}
.title{
  font-size:10px;
  color:#b3b3b3
}
.blue-icon{
  background-color: #8fddf5
}
.green-icon{
  background-color: rgba(117,190,58,255);
}
.purple-icon{
  background-color:rgba(124,56,188,255);
}

</style>
