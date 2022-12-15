# Object Oriented Programming:
* Object oriented programming and functional programming are paradigms that allow us to organize code
* Object oriented programming says that bringing together the data and its behavior in a single location
* Functional Programming says that data and behavior are distinctly different things and should be kept separate for clarity.
* functional programming says, just give me a data and I'll act upon that data through functions

## factory functions:
* As the name suggests, our functions that act like factories, they create objects for us.
```javascript
// factory function make/create object 
function createElf(name, weapon) {
    //we can also have closures here to hide properties from being changed.
    return {
      name: name,
      weapon: weapon,
      atack() {
        return 'atack with ' + weapon
      }
    }
}
const sam = createElf('Sam', 'bow');
const peter = createElf('Peter', 'bow');
  
console.log(sam.atack()); // atack with bow
```
* we have  issue of having same functionality on multiple objects
* There is one way of just doing this manually, right?
```javascript
const elfFunctions = {
    attack() {
      return 'atack with ' + this.weapon
    }
  }
function createElf(name, weapon) {
    return {
      name: name,
      weapon: weapon,
    }
}

const peter = createElf('Peter', 'bow');
peter.attack = elfFunctions.attack;
console.log(peter.attack()); // atack with bow
```
## another way is **Object.create**
```javascript
const elfFunctions = {
    attack: function() {
      return 'atack with ' + this.weapon
    }
}
  function createElf(name, weapon) {
    //Object.create creates __proto__ link with function elfFunction
    newElf = Object.create(elfFunctions)
    newElf.name = name;
    newElf.weapon = weapon
    return newElf
}
  
  
const sam = createElf('Sam', 'bow');
const peter = createElf('Peter', 'bow');

console.log(sam.attack()); // atack with bow
```
## Constructor Functions:
```javascript
function Elf(name, weapon) {
    this.name = name;
    this.weapon = weapon;
}
  
  
const sam = new Elf('Sam', 'bow');
const peter = new Elf('Peter', 'bow');
sam.name
```
* The new keyword automatically returns the object for us that we have here, and it creates the ELF constructor.
* any function that is invoked using the new keyword is called a constructor function.
```javascript
function Elf(name, weapon) {
  this.name = name;
  this.weapon = weapon;
}

Elf.prototype.attack = function() { 
  return 'atack with ' + this.weapon
}
const sam = new Elf('Sam', 'bow');
const peter = new Elf('Peter', 'bow');
sam.attack()
```
* when we use the new keyword Instead of this pointing to the window object, point this to the object that we just created.
* every function in JavaScript gets automatically a prototype property.
* we're use the prototype to add functionality to both Elf.
* We're able to use constructor functions instead of something like Object Create to create this magical function that creates a new object, returns a new object, and also modifies what this means to whatever object calls us.
## Class
```javascript
class Elf {
  constructor(name, weapon) {
    this.name = name;
    this.weapon = weapon;
  }
  attack() {
    return 'atack with ' + this.weapon
  }
}

const fiona = new Elf('Fiona', 'ninja stars');
console.log(fiona instanceof Elf) // 
const ben = new Elf('Ben', 'bow');
fiona.attack()
```
```javascript
// new binding
function Person(name, age) {
  this.name = name;
  this.age =age;
  console.log(this);
}

const person1 = new Person('Xavier', 55)

//implicit binding
const person = {
  name: 'Karen',
  age: 40,
  hi() {
    console.log('hi' + this.name)
  }
}

person.hi()

//explicit binding
const person3 = {
  name: 'Karen',
  age: 40,
  hi: function() {
    console.log('hi' + this.setTimeout)
  }.bind(window)
}

person3.hi()

// arrow functions
const person4 = {
  name: 'Karen',
  age: 40,
  hi: function() {
    var inner = () => {
      console.log('hi ' + this.name)
    }
    return inner()
  }
}

person4.hi()

```
## Inheritance:
```javascript
class Character {
  constructor(name, weapon) {
    this.name = name;
    this.weapon = weapon;
  }
  attack() {
    return 'atack with ' + this.weapon
  }
}

class Elf extends Character { 
  constructor(name, weapon, type) {
    // console.log('what am i?', this); this gives an error
    super(name, weapon) 
    console.log('what am i?', this);
    this.type = type;
  }
}

class Ogre extends Character {
  constructor(name, weapon, color) {
    super(name, weapon);
    this.color = color;
  }
  makeFort() { // this is like extending our prototype.
    return 'strongest fort in the world made'
  }
}

const houseElf = new Elf('Dolby', 'cloth', 'house')
//houseElf.makeFort() // error
const shrek = new Ogre('Shrek', 'club', 'green')
shrek.makeFort()

```

