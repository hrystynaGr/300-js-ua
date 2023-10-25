### Що таке деструктуризація?

Деструктуризація - оператор представлений в ES6 для полегшеного вилечення значень із обʼєктів. 

Деструктуризувати можна обʼєкти:
```
let person = {name: 'John', age: 25};
const {name, age} = person;
console.log(name, age) // 'John', 25
```

Вкладені обʼєкти:
```
let person = {name: {first: 'John', last: 'Doe'}, age: 25};
const {name: {first, last}, age} = person;
console.log(first, last, age) // 'John', 'Doe', 25
```

Деструктуризація масивів:
```
let arr = [34,56,7,8];
const [first, second] = arr;
console.log(first, second); // 34, 56
```

Деструктуризація вкладених масивів:
```
let arr = [3,[56,78],90];
const [first, [second, third]] = arr;
console.log(first, second, third) // 3, 56, 78
```

Пропускання елементів масиву:
```
let arr = [34,56,7,8];
const [first,,, last] = arr;
console.log(first, last); // 34, 8
```

> Деструктиризувати можна будь який ітеративний обʼєкт. На приклад- стрічку.
```
let str = 'Hello!';
const [first,,,,, last] = str;
console.log(first, last) // 'H' '!'
```