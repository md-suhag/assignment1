# Differences between interfaces and types in TypeScript

Hello! Typescript is very useful for project which provide many facilities. That's why it is used by developer all over the world. Today, we will learn differences between **interfaces** and **types** in TypeScript. Both are used for providing a structure object including many other features, flexibility, and different use case. So, let's deep dive into this topic...

## Type in typescript

By type we can use in primitive type, union types and type alias.

```
type ID = number;
type Status = "success" | "error";
```

```

type Person = {
	name: string;
	age:number
};
const person1:Person ={
	name:"rahim",
	age:20
}

type Product={
	name:string;
	description:string;
	category:string;
	price:number;
	inStock:boolean;
}
const product1:Product={
	name:'Apple Watch',
	description:'new apple watch',
	category:'watch',
	price:'700;,
	inStock:true
}
```

## Interface in typescript

we can use interface in object as well as classes.

```
interface  Product {
	name: string;
	description: string;
	category: string;
	price: number;
	inStock: boolean;
}

const  product1:  Product  = {
	name: "Apple Watch",
	description: "new apple watch",
	category: "watch",
	price: 700,
	inStock: true,
};


```

we can also extend interface easily as our needs.

```
interface  DiscountProduct  extends  Product {
	discountedPrice: number;
}

interface Shape{
	name: string;
	area(): number;
}

interface Rectangle extends Shape{
	width: number;
	height: number;
}

const rectangle1: Rectangle = {
	name: "Rectangle",
	width: 10,
	height: 5,
	area: function () {
	return this.width * this.height;
	}
};

console.log(rectangle1.area()); // 50

```

## conclusion

we have learnt different usage in this blog. By using type and interface properly, we can build large project.

=====================================================

# Union vs. Intersection Types in TypeScript

TypeScript's type system allows developers to combine types in two ways: **union types** and **intersection types**. These two features give us flexibility and control over how types are defined and used. Example of union and intersection type is given blew.

## Union Type

```
type  Role  = "frontend developer"|  "backenddeveloper"|  "full stack developer";

function  greetDeveloper(role:  Role) {
	console.log(`hi ${role}. Welcome aboard`);
}
greetDeveloper("frontend developer");

```

## Intersection Type

```
interface Person {
	name: string;
}

interface Employee {
	employeeId: number;
}

type Staff = Person & Employee;

const staffMember: Staff = {
	name: "Alice",
	employeeId: 101,
};



```
