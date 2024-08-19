## Factory Pattern

The Factory Pattern is a design pattern that provides a way to create objects in programming. Instead of creating objects directly using the `new` keyword and a constructor, you use a "factory" to do it for you. The factory acts as a machine that knows how to create the right type of object based on your requirements.

### Why Use the Factory Pattern?

- **Simplifies Your Code**: Instead of writing code everywhere to create different objects like dogs and cats, you centralize this creation process in the factory. If you need to change how objects are created, you only need to modify the factory.
  
- **Easier to Maintain**: If you want to add a new type of object, like a bird, you just update the factory. The rest of your code doesn’t need to change.

- **Hides Complexity**: If creating an object is complicated, the factory hides that complexity. You just ask the factory for an object, and it takes care of the details.

### When to Use It

- **Multiple Types**: When you have different types of objects to create and want to handle them in a uniform way.

- **Complex Creation**: When creating an object involves multiple steps or configurations.

- **Decoupling**: When you want to separate the creation of objects from the rest of your code.

### Example: Class-Based Factory

```javascript
class AnimalFactory {
  static createAnimal(type) {
    if (type === 'dog') {
      return new Dog();
    } else if (type === 'cat') {
      return new Cat();
    }
    return null;
  }
}

class Dog {
  speak() {
    return 'Woof!';
  }
}

class Cat {
  speak() {
    return 'Meow!';
  }
}

const myDog = AnimalFactory.createAnimal('dog');
const myCat = AnimalFactory.createAnimal('cat');

console.log(myDog.speak()); // Output: Woof!
console.log(myCat.speak()); // Output: Meow!
```
