<script setup lang="ts">
// типизация

// типизация переменных
// let count: number = 10;
// count = 20; // true
// count = "строка" // false


// типизация массиввов
// let userNames: string[] = ["xnj nj", "что то"];
// userNames.push("то то"); // true
// userNames.push(20); // false


// типизация обьектов
// let obj: {userName: string, age: number} = {
//   // userName: "какое то имя", // true
//   // age: 20 // true

//   // userName: 20, // false
//   // age: "какой то текст" // false
// }


// типизация функции
// function addNumbers(num:number, txt:string) : string{
//   return `${num} что то ${txt}`
// }
// addNumbers(10, "что то"); // true
// addNumbers("что то", 10); // false


// -----------------------------------------------------------------------------------


// Кортежи - массивы с фиксированной длинной и строго заданными типами по позициям

// Кортеж для описание пользователя 
// let user: [string, number];
// или 
// let user1: [name: string, age: number]; // тут все то же самое просто для удобство можешь имена им дать а так то же самое

// user = ["имя какое то", 10] // true
// user1 = ["имя какое то", 20] // true

// user = [10, "имя какое то"] // false
// user1 = ["имя какое то", 20, 20] // false (тк длинна больше чем нужно)


// Пример кортежа с функцией 
// function getUser(): [string, number]{
//   return ["nik", 10]; // true
//   return [10, "nik"]; // false
// }


// -----------------------------------------------------------------------------------


// Интерфейсы - способ определить свойства методы и тд в отдельной перменной

// интерфейс для обьекта 
// interface IAuter {
//   name: string;
//   age: number;
// }

// true
// const Autor: IAuter = {
//   name: "Джон"
//   age: 10
// }

// false
// const Autor: IAuter = {
//   name: 10,
//   age: "текст"
// }


// так же интерфейсы можно соединять
// interface ImainInfo {
//   name: string;
//   age: number;
// }

// interface IDectruct {
//   dest: string;
//   main: ImainInfo;
// }

// const autor: IDectruct = {
//   dest: "какая то строка",
//   main:{
//     name: "имя какое то",
//     age: 10
//   }
// }


// интерфейсы с массивами
// interface IAuter {
//   name: string;
//   age: number;
// }

// let autor: IAuter[] = [
//   {
//     name: "что то",
//    age: 10
//   }, 
//   {
//     name: "кто то",
//    age: 20
//   }
// ];


// -----------------------------------------------------------------------------------



</script>

<template>
  
</template>

<style scoped>

</style>
