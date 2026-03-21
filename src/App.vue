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


// Type Alias - Создаешь собственные типы и имеешь возможность их присваивать переменым и не только

// создаем tipe кортедж User 
// type TUser = [name: string, age: number];
// let user: TUser = ["кто то", 10]


// создаем type для функции 
// type TFun = [r: number, g: number, b: number];
// function rgb(fun: TFun): TFun{
//     return [fun[0], fun[1], fun[2]];
// }
// console.log(rgb([255, 255, 240]));


// создание type в обьектах
// type TUser = {
//     name: string,
//     age: number
// }
// let user: TUser = {
//     name: "кто то",
//     age: 10
// }


// -----------------------------------------------------------------------------------


// Union - обядинение типов (string | number | boolean) - либо это либо это 


// union в виде переменной 
// type TColor = string | number;
// let color: TColor = 10;
// или
// let color1: TColor = "red";


// union в ввиде массива
// type TRgb = [r: number | string, g: number | string, g: number | null];
// let rgb: TRgb = ["красный", 38, null];


// union в виде обьекта 
// type TCar = {
//     name: string | number,
//     mark: string | number,
//     cool: boolean
// }
// let car: TCar = {
//     name: 10,
//     mark: "мерсадес какой то",
//     cool: true
// }


// -----------------------------------------------------------------------------------


// Литеральные типы - это типы в которые можно писать то что изначально предпологается 

// литеральыне переменные 
// type TRole = "Admin" | "User" | "Creator";
// let role: TRole = "Admin"; // true
// let role: TRole = "ktoto"; // false 


// литеральная функция 
// type TMode = "light" | "dark";
// function Mode (m: TMode): void{
//     console.log(`в данный момент установлен mod = ${m}`);
// }
// Mode("light") // true
// Mode("что то") // false


// -----------------------------------------------------------------------------------


// Все виды операторов 

// readonly - только чтение
// в обьекте (в обьектах нужно задавать на кадое поле)
// type TUser = {
//     readonly id: number,
//     name: string;
// }
// let user: TUser = {
//     id: 10,
//     name: "джон"
// }
// user.id = 20 // false
// user.name = "андрей" // true


// в массиве  (в кортеджах нужно задавать на весь массив целиком а не на каждый элемент)
// let arr: readonly string[] = ["fdsfk'sd", "fsdkjs" , "и тд"]
// arr[0] = "xnj" // false

// пример с типом
// type TArray = readonly[user: string, age: number] 

// пример мы говорим что массив для чтение в котором будет обьект с определенными полями (можем менять сам обьект но не массив)
// const users: readonly {name: string, age: number}[] = [{
//     name: 'джон',
//     age: 20
// }]


// ? если есть пусть будет если нету то нечего страшного 
// function autoriz(name?:string) {
//     console.log(name, " привет");
// }
// autoriz("джон");
// autoriz();

// в типах
// type TUser = {
//     name: string,
//     patronom?: string
// }
// let user: TUser = {
//     name: "кто то",
//     patronom: "отчество"
// }
// или
// let user: TUser = {
//     name: "кто то",
// }


// | - или (мы уже знакомы)
// type TColor = string | number;
// let color: TColor = 10;


// & - и 
// type TName = {
//     name: string
// }
// type TAge = {
//     age: number
// }
// type TUser = TName & TAge
// let user: TUser = {
//     name: "кто то",
//     age: 10
// }


//! - не null


//  in перебор (уже знаком пербор массивово, Обьектов и тд)


// // ?? - если есть то присвой покажи и тд именно первое если нету то присвой покажи и тд второе 
// function autiriz(name: string): void{
//     console.log(name?? "привет гость "); // если переменная name не пестая вывести ее если она пуста то вывести привет гость 
// }
// autiriz("даня"); // даня
// autiriz(""); // привет гость


</script>

<template>
  
</template>

<style scoped>

</style>
