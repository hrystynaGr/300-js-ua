### Порівняйте підходи роботи з асинхронним кодом: сallbacks vs promises vs async/await.

**callbacks** - найстарший з трьох спосіб роботи з асинхронним кодом. Підтримується усіма API. Важкиц для читання код, використання колбеків може призвести до callback hell. Не має вюудованого механізму роботи із помилками.

```
function1(callback) {
    console.log('Step1!');
    callback();
}

function2(callback) {
    console.log('Step2!');
    callback();
}

function3(callback) {
    console.log('Step3!');
    callback();
}

step1(function() {
    step2(function() {
        step3(function(){
            console.log('Allsteps done!');
        });
    });
});
```

**promises** - новіший спосіб роботи із асинхронним кодом ніж колбеки. Легший для читаня код. Пілс явиконання асинхронної операції повертається обєкт типу проміс, який в майбутньому стане або даними які завантажлись або помилкою яка виникла у процесі іх завантаження. Має вбудований механізм роботи із помилками.

```
const data = new Promise((res, rej) => {
    if (fetchingSuccessful) {
        resolve(someData);
    } else {
        reject(someError);
    }
}).then((data) => do something with data)
.catch((error) => console.log(error))
```

**async/await** - найновіший спосіб роботи з асинхронним кодом який у своїй основі використовує проміси. Код виглядає як звтчайний синхронний код. Де ключове слово async використовується для позначення функції яка повертає проміс а ключове слово await використовується для очікування на те щоб проміс виконався.

```
async function sayHi() {
    let data = await functionThatCatchesData();
    console.log(data);
}
```

