<template>
    <tr class="car-data">
      <td width="250">
        <div class="car-id">{{car._id}}</div>
        <div>
            <img src="https://via.placeholder.com/250x125/d2d2d2/?text=no%20image%20yet" onerror="this.src='https://via.placeholder.com/250x125/d2d2d2/?text=no%20image%20yet';" :alt="this.car.brand+' '+this.car.brand" :title="this.car.brand+' '+this.car.brand" class="carImg" />
        </div>
      </td>

      <td>{{car.brand}}</td>
      <td>{{car.model}}</td>
      
      <td>{{car.engine.toFixed(1)}}</td>
      <td>{{car.price.toFixed(2)}} €</td>
      
      <td>
        <button class="car-remove btn  btn-danger" 
        @click="removeCar()">Delete <font-awesome-icon icon="trash" /></button>
        </td>
    </tr>
</template>

<script>
export default {
  props:['car', 'CARS'],
  name: 'Car',  
  data(){
    return {

    }
  },
  methods: {
    removeCar: function(){
      let carID = this.car._id;
      fetch(`http://localhost:5001/api/cars/${this.car._id}`, {
        method: 'DELETE',
        headers: {'Content-Type': 'application/json'},
        //body: JSON.stringify({id: '5bdcdfa40f0a326f858feae0'})
      })
      .then(response => response.json()).then(json=>{      
        if(json.status==='ok'){          
          let targetCar = this.CARS.find(function(x) {              
              return x._id === carID;
          });
          this.CARS.splice(this.CARS.indexOf(targetCar), 1);
        }
      })
    }
  }
}
</script>

<style lang="scss">
.car-data{
  .car-id{
    text-align: center;
    font-size:11px;
    color:#999;
    font-style: italic;
  }
}
</style>