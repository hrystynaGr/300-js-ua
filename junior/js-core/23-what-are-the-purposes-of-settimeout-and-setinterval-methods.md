### Для чого призначені методи setTimeout і setInterval?

Ці методи призначені для асинхронного програмування. 

**setTimeout** - виконує колбек функцію після того як часовий проміжок переданий до setTimeout - закінчився.
```
setTimeout(function, delay);
```
```
setTimeout(() => console.log('Hello, after 3 sec.'), 3000);
```

**setInterval** - виконує колбек функцію після кожного разу як закінчиться інтервал, допоки інтервал не буде видалено. 
```
setInterval(function, delay);
```
```
setInterval(() => console.log('Hello, each 3 sec.'), 3000); // infinite function
```
```
let message = 0;
const myTimer = setInterval(()=> {
    console.log(message++);
    if(message > 5) {
        clearInterval(myTimer)
    }
}
, 200)
```

#### Як setTimeout і setInterval працюють ʼпід капотомʼ?
1. Функція setTimeout викликається.
2. Колбек функція додається до колбек стеку.
3. Інтервал починає свій відрахунок.
4. *Event Loop* постійно перевіряє чи є щось у колбек стеку готове до виконання.
5. Інтервал закінчився і *Event Loop* підхоплює функцію і додає до стеку виконання.
6. Фнкція буде виконана як тільки стек буде вільний від попередніх функцій.