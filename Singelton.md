## Singleton Pattern

The Singleton pattern ensures that there is only one instance of a class and provides a single point to access that instance. It's useful when you want to share one resource, like a configuration or service, across your application.

### Function-Based Singleton

This method uses a special function to create and manage the single instance. It employs a closure to keep the instance private and only exposes a way to access it.

```
const singleton = (function () {
  let instance = null;

  function createInstance() {
    return { name: 'Rohit', age: 91, score: Math.floor(Math.random() * 10) }; 
  }

  return {
    getInstance: function () {
      if (!instance) {
        instance = createInstance();
      }
      return instance;
    }
  };
})();

const instance1 = singleton.getInstance();
const instance2 = singleton.getInstance();
console.log(instance1 === instance2); // true
```

---

### Class-Based Singleton

This method uses a JavaScript class to manage the single instance. It uses a static property to ensure that only one instance is created.

```
class Singleton {
  constructor() {
    if (!Singleton.instance) {
      Singleton.instance = this;
      this.name = 'Rohit';
      this.age = 91;
      this.score = Math.floor(Math.random() * 10);
    }
    return Singleton.instance;
  }
}

const instance1 = new Singleton();
const instance2 = new Singleton();
console.log(instance1 === instance2); // true
```

