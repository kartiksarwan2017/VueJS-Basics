<script setup lang="ts">

  //  let name = "Krishna";
  //  let age = 25;
  //  // false = Male  true = female
  //  let sex = false;

  //  age = 26;
  //  sex = "male";


  // let name:string = "Krishna";
  //  let age:number = 25;
  //  // false = Male  true = female
  //  let sex:boolean = false;

  //  age = 26;
  //  sex = "male";

  /* Situations in which we have to annotate the type */
  //  let name = "Krishna";
  //  let age = 25;
  //  // false = Male  true = female
  //  let sex = false;
  //  let occupation: string;

  //  occupation = "Software Developer";
  //  age = 26;
  //  sex = "male";


   /* annotate explicitly */
  //  const arrayOfNumbers: number[] = [];

  //  arrayOfNumbers.push("laith");
  //  arrayOfNumbers.push(true);
  //  arrayOfNumbers.push([]);
  //  arrayOfNumbers.push(2555);

  //  const myArr: (number | string)[] = [1, "two", 3, "four"];

  //  myArr.push("27");
  //  myArr.push(27);
  //  myArr.push(true);


  //  const employee: {
  //   name: string,
  //   age: number,
  //   sex: boolean,
  //   // occupation: string | undefined
  //   /* here occupation could be either string or undefined */
  //   occupation?: string
  //  } = {
  //   name: "Laith",
  //   age: 25,
  //   sex: false
  //  }

  //  employee.banana
  //  employee.name = 77; 
  //  employee.age = 7;

  //  employee.occupation = "Software Developer";


  /* Defining types using interface 
  interface is a way to write type for particular object
  */
  // interface Employee {
  //   name: string,
  //   age: number,
  //   sex: boolean,
  //   occupation?: string
  // }

  // const employee: Employee = {
  //   name: "Laith",
  //   age: 25,
  //   sex: false
  // }


  // interface Employee {
  //   name: string,
  //   age: number,
  //   sex: string,
  //   occupation?: string
  // }

  // const employee: Employee = {
  //   name: "Laith",
  //   age: 25,
  //   sex: "male"
  // }

  // employee.occupation = "Software Engineer";
  // employee.sex = "female";
  // employee.sex = "nonbinary";
  // employee.sex = "banana";  // irrelevant

  /* Using Enum */
  // enum GENDER {
  //   FEMALE,
  //   MALE,
  //   NONBINARY
  // }

  // interface Employee {
  //   name: string,
  //   age: number,
  //   sex: GENDER,
  //   occupation?: string
  // }

  // const employee: Employee = {
  //   name: "Laith",
  //   age: 25,
  //   sex: GENDER.FEMALE
  // }

  // employee.occupation = "Software Engineer";
  // employee.sex = GENDER.MALE;
  // employee.sex = GENDER.NONBINARY;
  // employee.sex = GENDER.BANANA; 

</script>

<template>
  <main>
    <!-- <h1>Guess My Favourite Number</h1>
    <input type="text" v-model="number" />
    <h1 v-if="number === '27'">YOU GUESS IT</h1> -->
    <!-- {{ typeof(number) }}
    {{ typeof(27) }} -->
  </main>
</template>

<style scoped>
</style>
