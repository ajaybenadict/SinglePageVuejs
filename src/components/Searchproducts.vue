<template>
  <div id="search-products" class="wrapperwhole">
    <h2>Search a Product</h2>
    <div class="wrapper">
      <form>
        <div class="details-area">
          <label>Product ID</label>
          <input type="text" v-model.lazy="products.id" required />
          <label>Product Name</label>
          <input type="text" v-model.lazy="products.name" />
          <label>Supplier ID</label>
          <select v-model="products.supplierId">
            <option
              class="option"
              v-for="supplierId in supplierIds"
              v-bind:key="supplierId"
            >{{supplierId}}</option>
          </select>
          <label>Category ID</label>
          <select v-model="products.categoryId">
            <option
              class="option"
              v-for="categoryId in categoryIds"
              v-bind:key="categoryId"
            >{{categoryId}}</option>
          </select>
          <label>Quantity Per Unit</label>
          <input type="text" v-model.lazy="products.quantityPerUnit" />
          <label>Unit Price</label>
          <input type="text" v-model.lazy="products.unitPrice" />
          <label>Units in Stock</label>
          <input type="text" v-model.lazy="products.unitsInStock" />
          <label>Units on Order</label>
          <input type="text" v-model.lazy="products.unitsOnOrder" />
          <label>Reorder Level</label>
          <input type="text" v-model.lazy="products.reorderLevel" />
          <label class="Checkbox">Discontinued</label>
          <input type="checkbox" />
          <button>Search</button>
          <button>Clear</button>
        </div>
        <div id="preview" class="previewmsg">
          <h3>Preview Search Items</h3>
          <p>Product ID</p>
          {{products.id}}
          <p>Product Name</p>
          {{products.name}}
          <p>Supplier ID</p>
          {{products.supplierId}}
          <p>Category ID</p>
          {{products.categoryId}}
          <p>Quantity Per Unit</p>
          {{products.quantityPerUnit}}
          <p>Unit Price</p>
          {{products.unitPrice}}
          <p>Units In Stock</p>
          {{products.unitsInStock}}
          <p>Units on Order</p>
          {{products.unitsOnOrder}}
          <p>Reorder Level</p>
          {{products.reorderLevel}}
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: {
        id: "",
        name: "",
        supplierId: "",
        categoryId: "",
        quantityPerUnit: "",
        unitPrice: "",
        unitsOnOrder: "",
        unitsInStock: "",
        reorderLevel: ""
      },
      supplierIds: ["Supplier 1", "Supplier 2", "Supplier 3", "Supplier 4"],
      categoryIds: ["Category 1", "Category 2", "Category 3", "Category 4"]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
}
h2 {
  text-align: center;
}
.wrapperwhole {
  width: 1000px;
  margin: 5% auto;
}
.previewmsg {
  display: flex;
  flex-direction: column;
  order: 2;
  flex: 1;
  min-width: 18em;
  background: rgba(0, 0, 0, 0.2);
  color: black;
  padding: 15px;
  border-radius: 25px;
}
p {
  font-weight: bold;
}
.wrapper form {
  display: flex;
  background: rgba(0, 0, 0, 0.2);
  border-radius: 25px;
  padding: 1.9em;
}
.details-area {
  flex: 1;
  order: 1;
  margin-right: 2em;
}
.details-area input,
.details-area select {
  width: 100%;
  height: 40px;
  background: transparent;
  color: black;
  border-radius: 40px;
  font-size: medium;
  outline: transparent;
  padding-left: 15px;
}
.option {
  width: 100%;
  height: 40px;
  background: rgba(0, 0, 0, 0.2);
  color: black;

  border-radius: 40px;
  font-size: medium;
  outline: transparent;
}
button {
  padding: 1em;
  margin: 10px;
  margin-top: 10px;
  margin-bottom: 1em;
  margin-right: 10px;
  background: tomato;
  color: #fff;
  border: 0;
  padding: 15px 40px;
  border-radius: 40px;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-size: 16px;
  text-transform: uppercase;
  outline: none;
}
button:hover {
  color: black;
  font-weight: bold;
  transition: ease-in 0.1s;
  cursor: pointer;
}
label {
  color: black;
  line-height: 40px;
}

input[type="checkbox"] {
  width: 20px;
  height: 20px;
  margin-top: 10px;
}
input[type="checkbox"]:hover {
  cursor: pointer;
}
</style>
