<!-- <template>
    <div>
        <ul>
            <li v-for="item in items" :key="item.id"> 
                {{ item.label }}
            </li>
        </ul>
    </div>
</template>

<style>

ul {
  list-style-type: none;
}

li {
  float: left;
  background-color: #F6E3CA;
  margin-right: 10px;
  border: #D7C8B6 2px solid;
  border-radius: 30%;
}
</style>

<script setup lang="ts">
    const items = ([
        {id: 1, label: "pizza"},
        {id: 2, label: "hamburguesa"},
        {id: 3, label: "panzerotti"}
    ])


</script> -->



<!-- <template>
    <div>

        <li v-for="item in menuLs">
  {{ item.menuName}} 
  <span v-for="subitem in item.menuProducts ">{{ subitem.productName }}</span>
</li>
    
    </div>
</template>

<style>
    ul {
  list-style-type: none;
}

li {
    background: linear-gradient(135deg, #6a11cb, #2575fc);
    color: white;
    padding: 15px;
    margin: 10px 0;
    border-radius: 10px;
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    position: relative;
}

span{
  background-color: #F6E3CA;
  margin-right: 10px;
  border: #D7C8B6 2px solid;
  border-radius: 30%;
  display: block;
}
</style>

<script setup lang="ts">
    const menuLs = [
        {
            menuName: "panzerottis", 
            menuProducts: [
                {
                    productName: "mexicano",
                    productPrice: 2000,
                    productIngredients:""
                }
            ]
        },
        {
            menuName: "pizzas", 
            menuProducts: [
                {
                    productName: "parche",
                    productPrice: 36000,
                    productIngredients:""
                },
                {
                    productName:"margarita",
                    productPrice:2000,
                    productIngredients:""

                }
            ]
        },
        {
            menuName: "hamburguesas", 
            menuProducts: [
                {
                    productName: "senciila",
                    productPrice: 36000,
                    productIngredients:""
                },
                {
                    productName:"doble carne",
                    productPrice:2000,
                    productIngredients:""

                }
            ]
        },
        
        
        
    ]
</script> -->

<template>
    <div>
        <ul>
            <li v-for="(item, index) in menuLs" :key="index">
                <div class="menu-header">
                    <span>{{ item.menuName }}</span>
                    <button @click="toggleMenu(index)">
                        {{ activeMenus[index] ? "Ocultar" : "Ver productos" }}
                    </button>
                </div>

                <ul v-if="activeMenus[index]" class="product-list">
                    <li v-for="(subitem, subIndex) in item.menuProducts" :key="subIndex">
                        <span>{{ subitem.productName }} - ${{ subitem.productPrice }} - {{ subitem.productIngredients }}</span>
                    </li>
                </ul>
            </li>
        </ul>
    </div>
</template>

<style>
body {
    font-family: Arial, sans-serif;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    background: linear-gradient(135deg, #000000, #000000);
    color: white;
    padding: 15px;
    margin: 10px 0;
    border-radius: 10px;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    position: relative;
}

li:hover {
    transform: translateX(5px);
}

.menu-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

button {
    background-color: #000000;
    border: none;
    padding: 8px 12px;
    color: white;
    cursor: pointer;
    border-radius: 5px;
    transition: background 0.3s;
}

button:hover {
    background-color: #e68900;
}

.product-list {
    margin-top: 10px;
    padding-left: 20px;
}

.product-list li {
    background-color: #F6E3CA;
    color: hsl(0, 0%, 100%);
    border-radius: 5px;
    padding: 8px;
    margin-bottom: 5px;
}
</style>

<script setup lang="ts">
import { ref } from "vue";

// Lista de menús con productos
const menuLs = ref([
    {
        menuName: "Panzerottis",
        menuProducts: [
            { productName: "Mexicano", productPrice: 2000 }
        ]
    },
    {
        menuName: "Pizzas",
        menuProducts: [
            { productName: "Parche", productPrice: 36000, productIngredients: "pollo, queso, tocineta, salsa dulce" },
            { productName: "Margarita", productPrice: 2000 },
            {productName: "campesina", productPrice: 50000}
        ]
    },
    {
        menuName: "Hamburguesas",
        menuProducts: [
            { productName: "Sencilla", productPrice: 36000 },
            { productName: "Doble carne", productPrice: 2000 }
        ]
    }
]);

// Estado de los menús abiertos
const activeMenus = ref(Array(menuLs.value.length).fill(false));

// Función para alternar la visibilidad de los productos
const toggleMenu = (index: number) => {
    activeMenus.value[index] = !activeMenus.value[index];
};
</script>
