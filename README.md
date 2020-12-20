# Typescript
Learning TypeScript


# Setting
npx tsconfig.json
yarn add -D @types/node typescript nodemon

package.json
"scripts":{
  "watch": "tsc -w",
  "start": "nodemon dist/index.js"
}

yarn watch, yarn start 둘다 켜두어야 함

# Types in typescript
const name = "joe", age = 24, gender = "male";
const sayHi = (name: string, age: number, gender: string): string => { 
  return `My name is ${name}. I'm ${age} years old and I'm ${gender}`
}
console.log(sayHi(name, age, gender));

-> name-string, age-number, gender-string, sayHi-string

# Interface

interface Human {
  name: string,
  age: number,
  gender: string
}

const person = {
  name: "Joe",
  age: 24,
  gender: "male"
}

const sayHi = (person: Human): string => {
  return `My name is ${name}. I'm ${age} years old and I'm ${gender}`
}

console.log(sayHi(person));

interface는 컴파일이 되지 않아 dist/index.js에는 들어가 있지 않다.
따라서 interface 대신 class를 사용할 수 있다.

# Class
constructor 는 생성자 매서드이며 클래스가 시작할 때 마다 호출된다.

class Human {
  public name: string;
  public age: number;
  public gender: string;
  constructor(name: string, age: number, gender: string) {
    this.name = name;
    this.age = age;
    this.gender = gender;
  }
}

const mike = new Human("Mike", 23, "male");

const sayHi = (person: Human): string => {
  return `My name is ${person.name}. I'm ${person.age} years old and I'm ${person.gender}`
}

console.log(sayHi(mike));

export { };