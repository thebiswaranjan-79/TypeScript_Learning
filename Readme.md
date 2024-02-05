## TypeScript 
=> Types in TypeScript 
    -> string = store text
    -> number = integers, real 
    -> boolean
    -> undefined
    -> null
    -> bigint
    -> symbol 
 These above types are Premitive types , you can't make any changes 
 
 let id = 5; // JS

TS => var<variable_name>   : number = <value>; // This is called as Type  Annotation or type signature 

let id : number = 5;
let firstName : string = "Biswa";
// let firstName = "Biswa" // it also works , it is not dumb 

## Types in typescript
=> classes
=> interface

## Function in TS
function sum(a : number,b : number) : number {
    return a+b;
}
console.log(sum(10,20));// 30

function sum1(a : number,b : string) : any {
    return a+b;
}
console.log(sum1(10,"Biswa")); // 10Biswa

- let say b is optional 
function sum2(a : number,b?: number) : number {
    return a+(b || 0); // if b is present return b otherwise tak eb is 0
}
console.log(sum2(78));// if you don't pass b it will take it undefined 


## Date and Any in TypeScript 
const dob = new Date(2003, 11, 12);
console.log(dob); // Date: "2003-12-11T18:30:00.000Z" 
console.log(dob.getDate()); // 12
console.log(dob.getHours());//0

## any type object 
example :  
    let x : any = 10;

    let x = 10 ;// work 
    x = "10";// not work => Type 'string' is not assignable to type 'number'.


    <!-- let x ; // No error 
    x = "10";
    x = 10; -->
- if you want oto define a variable with type any , then either mention " : any" while declaring the variable ot don't assign a value to the variable 

