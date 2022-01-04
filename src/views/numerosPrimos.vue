<template>
  <b-container>
    <b-row>
      <b-col>
        <h1>Calcula los números primos en un rango</h1>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <span class="form-input m-2"> Ingrese primer número del rango</span>
        <input id="num1" class="m-2" type="text" required />
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <span class="form-input m-2"> Ingrese segundo número del rango</span>
        <input id="num2" class="m-2" type="text" required />
      </b-col>
    </b-row>
    <b-row>
      <b-col lg="2" md="4" sm="8">
        <button @click="calculoNumerosPrimos()">calcula</button>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "Ejercicio1",
  data() {
    return {};
  },

  methods: {
    calculoNumerosPrimos() {
      let num1 = document.getElementById("num1").value;
      let num2 = document.getElementById("num2").value;

      function calcularPrimos() {
        let num1 = parseInt(document.getElementById("num1").value);
        let num2 = parseInt(document.getElementById("num2").value);
        let myPrimeArray = "";
        const Array = [];
        for (let i = 1; i <= num2; i++) {
          Array.push(i);
        }
        const arrayFiltered = Array.slice(num1 - 1, num2);
        myPrimeArray = arrayFiltered.filter((num) => {
          for (let i = 2; i < num; i++) {
            if (num % i == 0) return false;
          }
          return num !== 1;
        });
        if (myPrimeArray == "") {
          alert("En el rango seleccionado no se encuentran números primos");
          return false;
        } else {
          alert("los valores calculados son: " + myPrimeArray);
        }
      }

      if (
        num1 != "" &&
        num2 != "" &&
        parseInt(num1) > 0 &&
        parseInt(num2) > 0 &&
        parseInt(num2) > parseInt(num1) &&
        parseInt(num1) < parseInt(num2)
      ) {
        calcularPrimos();
      } else if (parseInt(num1) <= 0) {
        alert("Alerta, El valor en el primer campo debe ser mayor a cero");
        return false;
      } else if (num1 == "") {
        alert("Alerta, Debe ingresar algún valor en el primer campo");
        return false;
      } else if (num2 == "") {
        alert("Alerta, debe ingresar algún valor en el segundo campo");
        return false;
      } else if (parseInt(num2) <= 0) {
        alert("Alerta, El valor en el segundo campo debe ser mayor a cero");
        return false;
      } else if (parseInt(num1) > parseInt(num2)) {
        alert("Alerta, el rango de valores seleccionado no es valido");
        return false;
      } else if (parseInt(num1) == parseInt(num2)) {
        alert(
          "Alerta, el rango de valores seleccionado debe ser mayor entre sí"
        );
        return false;
      }
    },
  },
};
</script>

<style>
</style>