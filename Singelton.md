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
