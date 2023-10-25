#### Що таке область видимості?

**Область видимості** - частина коду у якікій можуть бути ооголошені та доступні змінні та чи функції.

Є два типи областей видимості:
**GlobalScope** - глобальна область видимості, до неї належить *global object* (window), змінні оголошені у глобальній області видимості стають даними глобального обʼєкту.
```
let person = { name: 'John', age: 25};
console.log(window.person) // { name: 'John', age: 25} 
```
**Local Scope** - локальна область видимості - функція чи блок. Змінна оголошена у блоці буде видимою лише у блоці.
```
function sayHi() {
    let length = 8;
    return length;
}
console.log(length); // ReferenceError
```