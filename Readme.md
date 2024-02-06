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

// The problem with any is that it starts behaving exactly as js data types

## void return type 
function fun() : void {
    console.log("If you don't want to return the function anything so you can give a type void ");
}
fun();

function fun() : (number | string) { // it is called union
    return "10";
}
fun();

## ENUMS or ENUMERATION
=> It is a tpe that represent named constants are know as enum 
=> let say u have a ticket, the ticket can have any state ["initial State", "Cancelled", "resolved]

=> When u are have limited times of possibility, instead of defining multiple strings and comparing them , we can use enum 

// Enums
enum TicketStatus {
    INITIALISED,
    CANCELLED,
    PENDING,
    CLOSED
}
console.log(TicketStatus.INITIALISED);// 0
console.log(TicketStatus.CANCELLED);// 1
console.log(TicketStatus.PENDING);// 2
console.log(TicketStatus.CLOSED);// 3

// It has mapped these values like indexing 

// Enums
enum TicketStatus {
    INITIALISED,
    CANCELLED,
    PENDING,
    CLOSED
}
const Ticket ={
    id:1,
    title : "new Ticket",
    status : TicketStatus.CANCELLED
}

console.log(Ticket); // 1
if(Ticket.status == TicketStatus.INITIALISED){
    console.log("Initialized Started ");
}else{
    console.log("I am in other States");
}


enum StatusCode {
    NotFound = 404,
    Success = 200,
    Accepted = 202,
    Created = 21,
    BadRequest = 400
}

const response = {
    url : "www.somithing.com",
    type : "GET",
    data : "Some String",
    status : StatusCode.Success
}
console.log(response); // 200 

## Type Inferring ##
const result = {
    name : "Sanket",
    marks : 98
}
// the type of the above object is inferred as {name : string, marks :number}
// something like the iven object below 

// const result : {name : string, marks : number} = {
//     name : "Sanket",
//     marks : 89
// }
console.log(result);

// updating an old key value pair
result.marks  = 90; // do you think TS allow this ? \

// adding a new key value pair 
result.address = "XYZ";

// Now the above stmt will throw a compilation error bcoz in the type {name : string, marks : number} 
// we never mention anything about any address.
// That's why TS thinking w are violationg the default property 


// To solve this , we can add an additional optional address property while defining the object;

// const result : { name : string, marks : number} = {
    // name : "Biswa",
    // marks : 79;
// }
