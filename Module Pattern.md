## Module Pattern

The Module Pattern is a design pattern in JavaScript that allows you to create modules with private and public properties and methods. It encapsulates code to protect it from the global scope, providing a way to organize and manage code, especially in large applications.

```javascript

const Module = (function () {
    // Private variables and methods
    let privateVar = 'I am private';

    function privateMethod() {
        console.log(privateVar);
    }

    // Public API
    return {
        publicVar: 'I am public',
        
        publicMethod: function () {
            console.log(this.publicVar);
            privateMethod(); // Accessing private method
        }
    };
})();

console.log(Module.publicVar); // Outputs: 'I am public'
Module.publicMethod(); // Outputs: 'I am public' and 'I am private'

// Accessing private variables or methods directly will result in an error
console.log(Module.privateVar); // Undefined
Module.privateMethod(); // Error: Module.privateMethod is not a function
```

```javascript
const CounterModule = (function () {
    let count = 0; // Private variable

    function logCount() {
        console.log(`Current count: ${count}`);
    }

    return {
        increment: function () {
            count++;
            logCount();
        },
        reset: function () {
            count = 0;
            logCount();
        }
    };
})();

CounterModule.increment(); // Current count: 1
CounterModule.increment(); // Current count: 2
CounterModule.reset();     // Current count: 0

// Trying to access count directly will fail
console.log(CounterModule.count); // Undefined

```
