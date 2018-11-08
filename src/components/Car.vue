<template>
    <tr>
      <td>
        <img src="https://via.placeholder.com/250x125/d2d2d2/?text=no%20image%20yet" onerror="this.src='https://via.placeholder.com/250x125/d2d2d2/?text=no%20image%20yet';" :alt="this.car.brand+' '+this.car.brand" :title="this.car.brand+' '+this.car.brand" class="carImg" />
      </td>

      <td>{{car._id}}</td>
      <td>{{car.brand}}</td>
      <td>{{car.model}}</td>
      
      <td>{{car.engine.toFixed(1)}}</td>
      <td>{{car.price.toFixed(2)}} €</td>
      
      <td>
        <button class="car-remove fas fa-trash-alt btn  btn-danger" 
        @click="removeCar()"></button>
        </td>
    </tr>
</template>

<script>
export default {
  props:['car'],
  name: 'Car',  
  data(){
    return {

    }
  },
  methods: {
    removeCar: function(){
      console.log(`remove ${this.car._id}`);
    }
  }
}
</script>