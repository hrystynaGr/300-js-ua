### Які існують типи даних у JS?

Типи даних діляться на дві групи, примітивні та cструктури. Серед примітивних:
1. *Boolean*
2. Number
3. String
4. BigInt
5. Undefined
6. *Symbol (ES6)*
Структури:
1. Object (Object, Array, *Map*, *Set*, *WeakMap*, *WeakSet*, Data etc.)
2. null (typeof null -> object, це була помилка у ранніх версіях ES, вона залишилась досі для того щоб старі версіїї були сумісні з новими страндартами)

1. **Boolean**
```
Boolean(false) //false
Boolean(0) //false
Boolean('') //false
Boolean(undefined) //false
Boolean(null) //false
```
6. **Symbol** - новий примітивний немутабельний тип даних, представлений у ES6. Символи завжди унікальні, навіть якщо для їх створення використовувався однаковий дескриптор.
```
const s1 = Symbol('hey');
const s2 = Symbol('hey');
s1 === s2 // false
```
Саме тому символи часто застосовують як ключі для об'єктів для більшої ізольованості і запобігання мутаціям:
```
const person = {
    name: 'Jake', 
    age: 27,
    id: 2574
}
// Тепер будь-яка стороння програма, яка має доступ до цих даних, запускає `person.id = 2`
// Тепер значення person.id - 2.
```
Щоб уникнути такої поведінки, вткористаємо символ для ключа id
```
const id = Symbol('id')
const person = {
    name: 'Jake', 
    age: 27,
    [id]: 2574
}
// Тепер будь-яка стороння програма, яка має доступ до цих даних, запускає `person.id = 2`
// Тепер значення person.id залишається 2574
```
Методи для роботи з символами:
```
const x = Symbol('x') //create symbol
console.log(x) // Symbol('x')
console.log(x.description()) // 'x'
```

> for...in цикл не враховує символи. 
```
for (let key in person) {
    console.log(key)
}
```
Результат:
```
name
age
```

#### **Map** 
**Map** - тип даних, схожий на звичайний об'єкт, але ключем може бути будь-який тип даних.
```
let recipe = new Map();
```
Додати значення до Map. Оскільки метод set() повертає Map, ми можемо "ланцюгувати" ці методи один за одним:
```
recipe.set('lemons', 100,).set(['sugar', 'vanillaSugar'], 100);
```
Повертає значення за ключем:
```
recipe.key(['sugar', 'vanillaSugar']) // 100
```
Повертає true/false в залежності чи існує таке значення в Мар чи ні:
```
recipe.has('lemons') // true
recipe.has('strawberries') // false
```
Видалити пару ключ-значення. Повертає true/false в залежності від того, чи було таке значення в Map до видалення:
```
recipe.delete('lemons') 
```
Видаляє все з Мар:
```
recipe.clear()
```
Повертає розмір Мар:
```
recipe.size
```
Для перебору значень можна використовувати наступні методи:
```
recipe.keys()
recipe.values()
recipe.entries()
```
або `forEach()` метод.

#### **Set** 
**Set** - мутабельний тип даних, схожий на масив, але всі значення в ньому унікальні. Іншими словами, одне і те саме значення може зустрічатися тільки один раз. Іншими словами, одне і те саме значення може зустрічатись тільки раз.
Методи для роботи із **Set**
Створити Set:
```
let recipe = new Set(); // пустий Set або
let schedule = new Set(['laundry', 'work', 'sport', 'work', 'sport', 'meal prep']);
console.log(schedule.size) // 4 
// тому що сет має такі значення:
// ['laundry', 'work', 'sport', 'meal prep'] 
// дублікати видалились
```
Додати значення до Set. Оскільки метод add() повертає Set, ми можемо "ланцюгувати" ці методи один за одним:
```
schedule.add('study').add('run');
```
Повертає true/false в залежності чи існує таке значення в Set чи ні:
```
schedule.has('work') // true
schedule.has('strawberries') // false
```
Видалити значення. Повертає true/false в залежності від того, чи було таке значення в Set до видалення:
```
schedule.delete('lemons')  //false
```
Видаляє все з Set:
```
schedule.clear()
```
Повертає розмір Set:
```
schedule.size
```
Для перебору значень можуть використовуватись наступні значення:
```
recipe.values()
recipe.entries()
```
або `forEach()` метод.

#### **WeakMap** 
**WeakMap** - тип даних, схожий на Map, але ключами можуть бути лише об'єкти. Коли на об'єкт-ключ немає посилань з інших місць, окрім WeakMap, то пара ключ-значення, ключем якої був цей об'єкт, видаляється.
```
let map = new WeakMap();
const obj1 = {1:1};
const obj2 = {2:2};
map.set(obj1, '1').set(obj2, '2');
obj2 = null;
map.has({2:2}) //false
```
Методів для ітерації через WeakMap не існує.
Методи для роботи з WeakMap:
```
let map = new WeakMap();
map.set();
map.has();
map.delete();
map.get();
```

**Caching with Objects as Keys:**
WeakMap можна використовувати для реалізації механізму кешування, де об'єкти служать ключами, і асоційовані дані зберігаються в кеші. Це корисно, коли вам потрібно кешувати результати для конкретних об'єктів і автоматично видаляти їх, коли об'єкти більше не використовуються.

**Garbage Collection Assistance:**
WeakMap може бути використаний для допомоги при зборі сміття в ситуаціях, де вам потрібно асоціювати дані з об'єктами, так, що коли об'єкти будуть видалені, дані видаляться автоматично також.

**Private Data for Objects:**
```
const privateData = new WeakMap();

class MyClass {
  constructor() {
    privateData.set(this, { key: 'value' });
  }

  getData() {
    return privateData.get(this);
  }
}

const obj = new MyClass();
console.log(obj.getData()); // { key: 'value' }

// When obj is no longer reachable, the associated data will be automatically garbage collected.
```

#### **WeakSet** 
**WeakSet** - тип даних, як і Set, але елементами можуть бути лише об'єкти, коли на елемент-ключ нема посилань з інших місць ніж WeakSet, то цей елемент з WeakSet видаляється.

Методів для ітерації через WeakSet не існує.
Методи для роботи з WeakSet:
```
let set = new WeakSet();
set.set();
set.has();
set.delete();
set.get();
```