<div align="center">
  <img width="625" height="268" src="https://github.com/ninja-js/js-interview/blob/master/img/ninja_inter.png">
  <h1>Вопросы и ответы для собеседования Front-end/JS разработчика и не только</h1>
  <h5>Хотите подготовиться к собеседованию по JavaScript и ищете вопросы, на которых можно попрактиковаться? Если так — считайте, что ваши поиски окончены.</h5>
</div>

Мы собрали много вопросов по JavaScript, предназначенных для тех, кто хочет превратиться из джуниора в сеньора, для тех, кто стремится успешно пройти собеседование в сфере фронтенд-разработки и получить интересное предложение от работодателя.

## Содержание

0. [Послесловие](#epilogue)
1. [Какие навыки необходимо обязательно подтянуть для собеседования?](#wtf_skills)
2. [Объясните особенности проверки равенства значений в JavaScript.](#one)
3. [Приведите примеры приведения к логическому типу значений, не относящихся к этому типу](#two)
4. [Что такое IIFE?](#4)
5. [Когда следует использовать стрелочные функции, которые появились в ES6?](#5)
6. [В чём разница между ES6-классами и конструкторами функций?](#6)
7. [Расскажите о методе Function.prototype.bind().](#7)
8. [Для чего обычно используются анонимные функции?](#8)
9. [В чём разница между методом Object.freeze() и ключевым словом const?](#9)
10. [Что такое «генератор»?](#10)
11. [Когда стоит использовать генераторы?](#11)
12. [Что такое «поднятие переменных»?](#12)
13. [Что выведет следующий код?](#13)
14. Что такое всплытие событий?
15. Что такое перехват событий?
16. Можете ли вы объяснить каждую часть URL?
17. В чем разница между npm и npx?
18. Что такое WebAssembly?
19. Как работает CSS Flexbox?
20. Что такое AJAX и для чего он нужен?
21. Что такое JAMstack и как с ним работать?
22. [Что такое «временная мёртвая зона» в ES6?](#22)
23. [Можете ли вы описать основное различие методов массивов forEach () и map ()? В каких ситуациях вы предпочли бы один из этих методов другому?](#23)
24. [Расскажите о шаблоне проектирования «Прототип»](#24)
25. [Чем отличаются друг от друга необъявленная переменная, переменная, содержащая значение null, и undefined-переменная? Как проверить переменную на предмет того, что она необъявлена, а также на null и undefined?](#25)
26. [Расскажите о шаблоне проектирования «Открытый модуль»](#26)
27. [В чём разница между объектами Map и WeakMap?](#27)
28. [Как в JavaScript-функции передаются параметры: по ссылке или по значению?](#28)
29. [Как организовать «глубокую заморозку» объекта?](#29)
30. [Почему JavaScript-программисты испытывают проблемы при использовании ключевого слова this?](#30)
31. [Сравните использование конструкции async/await и генераторов для реализации одного и того же функционала.](#31)
32. [Напишите функцию сложения вида add(num1)(num2).](#32)
33. [Что выведется в консоль ? Объясните почему.](#33)
34. 

### <a name="wtf_skills"></a> Какие навыки необходимо обязательно подтянуть для собеседования?

К любому собеседованию нельзя быть готовым на 100%. Давайте рассмотрим несколько пунктов, чтоб чувствовать себя немного увереннее.

- Самое основное правило, это умение читать код. В сложных ситуациях это поможет Вам быстрее выявить проблему и устранить ее.
- Обязательно подтяните свои навыки при работе с регулярными выражениями. Регулярные выражения могут быть довольно непростыми. Тем не менее они могут сделать для вас многое. Наиболее очевидный вариант использования - поиск определенных фрагментов текста в больших кодовых базах.
- Еще одним, не менее важным пунктом является знание терминологии. Попробуйте выписать все термины, которые вы знаете и кратко рассказать о каждом.

### <a name="one"></a> Объясните особенности проверки равенства значений в JavaScript

В JavaScript есть два оператора для проверки равенства величин. Первый — это так называемый оператор строгого равенства. Второй — оператор нестрогого равенства, при использовании которого может производиться преобразование типов проверяемых величин.

- Оператор __строгого равенства__ `(===)` проверяет значения на равенство, не выполняя при этом преобразования типов.
- Оператор __нестрогого равенства__ `(==)` проверяет значения на равенство, выполняя их приведение к общему типу.

```js
const a = "42";
const b = 42;

a == b;         // true
a === b;        // false
```

Вот некоторые правила, касающиеся использования различных операторов проверки равенства в JavaScript:

- Если любое из сравниваемых значений может быть значением `true` или `false` — постарайтесь избегать оператора `==`. Используйте оператор `===`.
- Используйте оператор `===` в том случае, если работаете со следующими значениями: `0`, `""` или `[]` (пустой массив).
- Во всех остальных случаях можете безопасно использовать оператор `==`. Причём, это не только безопасно, но и способствует упрощению кода и улучшению его читабельности.

### <a name="two"></a>  Приведите примеры приведения к логическому типу значений, не относящихся к этому типу

Суть этого вопроса в том, чтобы выяснить, какие значения, в случае преобразования их к логическому типу, превращаются в `false`, а какие — в `true`.

Вот список значений, которые можно назвать __ложными__ (falsy). Они, при преобразовании к логическому типу, превращаются в значение `false`:

- `""` (пустая строка).
- `0, -0, NaN` (не-число).
- `null, undefined`.

Любое значение, которое не входит в этот список, при его преобразовании к логическому типу, превращается в `true` (такие значения называют __истинными__ — truthy). Например:

- `"hello"`.
- `42`.
- `[ ], [ 1, «2», 3 ]` (массивы).
- `{ }, { a: 42 }` (объекты).
- `unction foo() { .. }` (функции).

### <a name="4"></a> Что такое IIFE?

IIFE (Immediately Invoked Function Expression) — это немедленно вызываемое функциональное выражение. Такое выражение выполняется немедленно после создания.

```js
(function IIFE(){
    console.log("Hello, World!");
})();
// "Hello, World!"
```

Этот паттерн часто используется для того чтобы не допустить загрязнения глобального пространства имён. Дело в том, что переменные, объявленные в IIFE (как и в любой другой обычной функции), невидимы за пределами этой функции.

### <a name="5"></a> Когда следует использовать стрелочные функции, которые появились в ES6?

Вот простые правила по использованию различных способов объявления функций, которыми я руководствуюсь, разрабатывая код для сред, поддерживающих стандарт ES6 и более новые стандарты:

- Используйте ключевое слово function в глобальной области видимости и для свойств `Object.prototype`.
- Используйте ключевое слово function для конструкторов объектов.
- В остальных случаях используйте стрелочные функции.

Как видите, стрелочные функции рекомендуется использовать практически везде. У такого положения дел есть несколько причин:

- Удобная работа с контекстом. Стрелочные функции используют значение `this` окружающего контекста, не имея собственного `this`. Если такие функции применяются последовательно, без использования обычных функций в сложных конструкциях, это обеспечивает безопасную работу с контекстом.
- Компактность. Код стрелочных функций легче вводить и легче читать. Возможно, это преимущество стрелочных функций перед обычными покажется вам спорным и зависящим от точки зрения каждого конкретного разработчика.
- Ясность кода. Если практически весь код представлен стрелочными функциями, любая обычная функция выделяется в таком коде тем, что создаёт собственный контекст. Применяя стрелочные функции, программист создаёт более понятный код, в котором легче, чем в коде без стрелочных функций, работать с `this`.

### <a name="6"></a> В чём разница между ES6-классами и конструкторами функций?

Сначала рассмотрим примеры.

Функция-конструктор:

```js
function Person(name) {
  this.name = name;
}
```

ES6-класс:

```js
class Person {
  constructor(name) {
    this.name = name;
  }
}
```

Если речь идёт о создании простых объектов, то конструкторы и классы, используемые для этой цели, выглядят очень похоже.

Основная разница между конструкторами и классами проявляется при использовании наследования. Если нам нужно создать класс Student, являющийся подклассом класса Person, и добавить к этому новому классу поле studentId, то вот как будет выглядеть код, в котором используются конструкторы, и код, в котором применяются классы.

Функция-конструктор:

```js
function Student(name, studentId) {
  // Вызываем конструктор суперкласса для инициализации полей, унаследованных от него.
  Person.call(this, name);

  // Инициализация собственных полей объекта.
  this.studentId = studentId;
}

Student.prototype = Object.create(Person.prototype);
Student.prototype.constructor = Student;
```

ES6-класс:

```js
class Student extends Person {
  constructor(name, studentId) {
    super(name);
    this.studentId = studentId;
  }
}
```

### <a name="7"></a> Расскажите о методе Function.prototype.bind ()

Процитируем MDN: «Метод bind() создаёт новую функцию, которая при вызове устанавливает в качестве контекста выполнения this предоставленное значение. В метод также передаётся набор аргументов, которые будут установлены перед переданными в привязанную функцию аргументами при её вызове».

Полагаю, что метод `.bind()` особенно полезен для привязки значения `this` в методах классов, которые нужно передавать в другие функции. Этот приём часто используется в React-компонентах.

### <a name="8"></a> Для чего обычно используются анонимные функции?

Анонимные функции используются при создании IIFE — конструкций, переменные, объявленные в которых, не загрязняют глобальную область видимости.

```js
(function() {
  // Какой-то код.
})();
```

Анонимные функции применяют в качестве функций обратного вызова, которые используются лишь в одном месте программы. Код будет выглядеть более самодостаточным и читабельным в том случае, если коллбэк будет объявлен прямо в том месте, где он используется. Это избавляет от необходимости просматривать код в поиске тела функции.

```js
setTimeout(function() {
  console.log('Hello world!');
}, 1000);
```

Анонимные функции удобно использовать в конструкциях, характерных для функционального стиля программирования, или при работе с библиотеками вроде `Lodash` (этот вариант их использования похож на их применение в качестве коллбэков).

```js
const arr = [1, 2, 3];
const double = arr.map(function(el) {
  return el * 2;
});
console.log(double); // [2, 4, 6]
```

### <a name="9"></a> В чём разница между методом Object.freeze () и ключевым словом const?

Ключевое слово `const` и `метод Object.freeze()` — это совершенно разные вещи.

Ключевое слово const применяется к привязкам (к «переменным»). Оно создаёт иммутабельную привязку, то есть — к переменной (константе), объявленной с помощью ключевого слова const, нельзя привязать что-то новое. Константе нельзя присвоить новое значение.

```js
const person = {
    name: "Leonardo"
};
let animal = {
    species: "snake"
};
person = animal; // Uncaught TypeError: Assignment to constant variable.
```

Метод `Object.freeze()` работает со значениями. А точнее — с объектными значениями. Он делает объект иммутабельным, что защищает от изменений значения свойств этого объекта.

```js
let person = {
    name: "Leonardo"
};
Object.freeze(person);
person.name = "Lima"; // Uncaught TypeError: Cannot assign to read only property 'name' of object
console.log(person);
```

Обратите внимание на то, что сообщение об ошибке выводится в строгом режиме. В обычном режиме операция изменения свойства "замороженного" объекта просто не срабатывает.

### <a name="10"></a> Что такое «генератор»?

__Генераторы__ — это функции, из которых можно «выходить», и в которые можно «входить» по мере необходимости. Их контекст (привязки переменных) сохраняется между сеансами "входа" в них. Генераторы объявляют с использованием ключевого слова `function*`. Такая функция, при её первом вызове, не выполняет код, возвращая особый объект, генератор, который позволяет управлять её выполнением. Для получения очередного значения, выдаваемого генератором, нужно вызвать его метод `next()`. Благодаря этому выполняется код функции до тех пор, пока в нём не встретится ключевое слово `yield`, возвращающее значение.

Функцию-генератор можно вызывать сколько угодно раз. Каждый раз будет возвращаться новый генератор. Но каждый генератор можно обойти лишь один раз.

```js
function* makeRangeIterator(start = 0, end = Infinity, step = 1) {
    let iterationCount = 0;
    for (let i = start; i < end; i += step) {
        iterationCount++;
        yield i;
    }
    return iterationCount;
}
```

### <a name="11"></a> Когда стоит использовать генераторы?

Если в двух словах описать основные полезные возможности генераторов, то окажется, что они заключаются в следующем:

- Код, в котором используется генератор, сам определяет момент получения следующего значения. Генератор отвечает только за возврат значений, управление им осуществляется извне.
- Существуют асинхронные генераторы. Они позволяют работать с асинхронными потоками данных.

Главное в генераторах — это то, что получить следующее значение, возвращаемое генератором, можно только тогда, когда оно нужно в коде, использующем генератор. Генераторы не возвращают всё за один раз. В некоторых ситуациях эта их особенность может оказаться весьма удобной.

### <a name="12"></a> Что такое «поднятие переменных»?

Сущность концепции «поднятия переменных» заключается в том, что объявления «поднимаются» в верхнюю часть текущей области видимости. В результате переменной можно воспользоваться до её объявления. Поднимаются лишь объявления переменных, но не код их инициализации. Обратите внимание на то, что поведение переменных, объявляемых с использованием ключевого слова `var`, отличается от поведения переменных и констант, объявленных с использованием `let` и `const`.

### <a name="13"></a> Что выведет следующий код?

```js
const output = (function(x) {
  delete x;
  return x;
})(0);

console.log(output);
```

Этот код выведет 0. Оператор delete используется для удаления свойств объектов. А x — это не свойство объекта — это локальная переменная. Оператор `delete` не воздействует на локальные переменные.

```js
const Employee = {
  company: 'xyz'
}
const emp1 = Object.create(Employee);
delete emp1.company
console.log(emp1.company);
```

Этот код выведет `xyz`. Свойство company является не свойством объекта `emp1`, а свойством его прототипа. Оператор `delete` не удаляет свойства прототипов объектов. У объекта `emp1` нет собственного свойства `company`. Проверить это можно так:

```js
console.log(emp1.hasOwnProperty('company')); // false
```

Если нам всё же необходимо удалить это свойство — сделать это можно, либо напрямую обратившись к объекту `Employee (delete Employee.company)`, либо — обратившись к прототипу объекта `emp1`, воспользовавшись его свойством `__proto__ (delete emp1.__proto__.company)`.


### <a name="22"></a> Что такое «временная мёртвая зона» в ES6?

В ES6 выполняется подъём переменных и констант, объявленных с использованием ключевых слов let и const (выполняется и подъём сущностей, объявленных с использованием ключевых слов var, class и function). Однако в коде имеется зона, простирающаяся от входа в область видимости до объявления переменной или константы. При обращении к переменной или константе в этой зоне будет выдана ошибка. Это и есть «временная мёртвая зона» (Temporal Dead Zone, TDZ).

```js
//console.log(aLet)  // выбросит ReferenceError

let aLet;
console.log(aLet); // undefined
aLet = 10;
console.log(aLet); // 10
```

### <a name="23"></a> Можете ли вы описать основное различие методов массивов forEach () и map ()? В каких ситуациях вы предпочли бы один из этих методов другому?

Для того чтобы понять разницу между этими методами — поговорим об особенностях работы каждого из них.

Вот как работает `.forEach()`:

- Он перебирает элементы массива.
- Он выполняет переданную ему функцию обратного вызова для каждого элемента массива.
- Он ничего не возвращает.

```js
const a = [1, 2, 3];
const doubled = a.forEach((num, index) => {
  // Сделать что-то с num и/или с index.
});

// doubled = undefined
```

Вот краткая характеристика метода `.map()`:

- Он перебирает элементы массива.
- Он преобразует каждый элемент исходного массива в элемент нового массива, вызывая переданную ему функцию для каждого элемента исходного массива.

```js
const a = [1, 2, 3];
const doubled = a.map(num => {
  return num * 2;
});

// doubled = [2, 4, 6]
```

В результате оказывается, что основное различие между `.forEach()` и `.map()` заключается в том, что `.map()` возвращает новый массив. Если вам нужно получить результат преобразования элементов исходного массива, не меняя этот массив, тогда стоит выбрать `.map()`. Если же нужно просто перебрать элементы массива — тогда можно воспользоваться `.forEach()`.

### <a name="24"></a> Расскажите о шаблоне проектирования «Прототип»

__Прототип (Prototype)__ — это порождающий шаблон проектирования. Он используется для создания объектов. Объекты, созданные с его помощью, содержат значения, скопированные из их прототипа (из объекта-образца). Этот шаблон ещё называют шаблоном Свойства (`Properties`).

Пример использования паттерна «прототип» — это инициализация неких объектов стандартными значениями, хранящимися в базе данных. Такие значения, записанные в прототип, копируются в новые объекты без обращения к базе данных.

Надо отметить, что этот паттерн редко используется в классических языках. В JavaScript применяется модель прототипного наследования. Данный паттерн применяется при конструировании новых объектов и их прототипов.

### <a name="25"></a> Чем отличаются друг от друга необъявленная переменная, переменная, содержащая значение null, и undefined-переменная? Как проверить переменную на предмет того, что она необъявлена, а также на null и undefined?

Необъявленная переменная создаётся при назначении значения идентификатору, который не был ранее объявлен с использованием `var`, `let` или `const`. Необъявленные переменные объявляются в глобальной области видимости, за пределами текущей области видимости. В строгом режиме при попытке назначения значения необъявленной переменной будет выброшено исключение `ReferenceError`. Использовать необъявленные переменные не рекомендуется — так же, как не рекомендуется использовать глобальные переменные. Их стоит всеми силами избегать. Для того чтобы обезопасить себя от последствий использования необъявленных переменных, воспользуйтесь блоком `try/catch`.

```js
function foo() {
  x = 1; // Выбрасывает в строгом режиме ReferenceError
}

foo();
console.log(x); // 1
```

Переменная, содержащая `undefined` — это объявленная переменная, которой не назначено некое значение. Значение `undefined` образует собственный тип данных. Если функция ничего не возвращает, и при этом результат её вызова записывается в переменную, то в эту переменную попадёт `undefined`. Для того чтобы организовать проверку на `undefined`, можно воспользоваться оператором строгого равенства (`===`) или оператором typeof, который возвратит строку `undefined`. Обратите внимание на то, что при проверке на `undefined` не следует пользоваться оператором нестрогого равенства (`==`), так как он считает равными значения `undefined` и `null`.

```js
let foo;
console.log(foo); // undefined
console.log(foo === undefined); // true
console.log(typeof foo === 'undefined'); // true

console.log(foo == null); // true. Не используйте такую конструкцию для проверки на undefined!

function bar() {}
let baz = bar();
console.log(baz); // undefined
```

Переменная, содержащая значение `null`, должна быть явным образом установлена в это значение. Она символизирует отсутствие значения и отличается от undefined-переменной тем, что значение, находящееся в ней, было ей явным образом назначено. Для того чтобы проверить значение на `null`, достаточно воспользоваться оператором строгого равенства. Для проверки на `null`, как и в случае с проверкой на `undefined`, не следует пользоваться оператором нестрогого равенства, считающим равными значения `null` и undefined.

```js
let foo = null;
console.log(foo === null); // true
console.log(typeof foo === 'object'); // true

console.log(foo == undefined); // true Не используйте такую конструкцию для проверки на null!
```

Я стараюсь никогда не оставлять переменные в необъявленном состоянии, или в состоянии, когда они объявлены, но им явным образом не назначено никакого значения. Если я не собираюсь записывать в переменную какое-то значение сразу после её объявления, я записываю в неё `null`. Если вы пользуетесь линтером, то он обычно сообщает о случаях использования необъявленных переменных.

### <a name="26"></a> Расскажите о шаблоне проектирования «Открытый модуль»

Шаблон "Открытый модуль" (Revealing Module) является разновидностью шаблона «Модуль» (Module). Цель использования этого шаблона заключается в поддержке инкапсуляции и в открытии некоторых свойств и методов, возвращённых в объектном литерале. Вот как будет выглядеть непосредственная реализация этого шаблона:

```js
const Exposer = (function() {
  let privateVariable = 10;

  let privateMethod = function() {
    console.log('Inside a private method!');
    privateVariable++;
  }

  let methodToExpose = function() {
    console.log('This is a method I want to expose!');
  }

  let otherMethodIWantToExpose = function() {
    privateMethod();
  }

  return {
      first: methodToExpose,
      second: otherMethodIWantToExpose
  };
})();

Exposer.first();        // Вывод: This is a method I want to expose!
Exposer.second();       // Вывод: Inside a private method!
Exposer.methodToExpose; // undefined
```

Очевидный недостаток этого шаблона заключается в том, что при его использовании нельзя обращаться к приватным методам.

### <a name="27"></a> В чём разница между объектами Map и WeakMap?

Эти объекты ведут себя по-разному в том случае, если переменная, содержащая ссылку на объект, являющийся ключом одной из пар ключ/значение, оказывается недоступной. Вот пример:

```js
const map = new Map();
const weakmap = new WeakMap();

(function() {
    let a = {
        x: 12
    };
    let b = {
        y: 12
    };

    map.set(a, 1);
    weakmap.set(b, 2);
})()
```

После того, как завершается выполнение `IIFE`, у нас уже не будет доступа к объектам `a` и `b`. Поэтому сборщик мусора удаляет ключ b из weakmap и очищает память. А вот содержимое map остаётся при этом неизменным.

В результате оказывается, что объекты WeakMap позволяют сборщику мусора избавляться от тех своих записей, на ключи которых нет ссылок во внешних переменных. Объекты map хранят пары ключ/значение вне зависимости от наличия или отсутствия внешних ссылок на ключи. То же самое можно сказать и о реализации структуры данных `Map` с использованием обычных массивов. В `WeakMap` используются «слабые» ссылки на ключи. Они не препятствуют работе сборщика мусора в том случае, если на объект, используемый в роли ключа, нет других ссылок.

### <a name="28"></a> Как в JavaScript-функции передаются параметры: по ссылке или по значению?

Параметры всегда передаются по значению, но в переменные, представляющие объекты, записаны ссылки на объекты. Поэтому, когда в функцию передают объект и меняют свойство этого объекта, это изменение сохраняется в объекте и при выходе из функции. В результате возникает ощущение того, что параметры в функции передаются по ссылке. Но если изменить значение переменной, представляющей объект, это изменение не повлияет на объекты, находящиеся за пределами функции.

Вот пример:

```js
function changeStuff(a, b, c)
{
  a = a * 10;
  b.item = "changed";
  c = {item: "changed"};
}

var num = 10;
var obj1 = {item: "unchanged"};
var obj2 = {item: "unchanged"};

changeStuff(num, obj1, obj2);

console.log(num);
console.log(obj1.item);
console.log(obj2.item);

// Вот что выведет этот код:

10
changed
unchanged
```

### <a name="29"></a> Как организовать «глубокую заморозку» объекта?

Для того чтобы обеспечить «глубокую заморозку» объекта с использованием Object.freeze(), нужно создать рекурсивную функцию, которая «замораживает» свойства объекта, которые также являются объектами.

Вот пример обычной «заморозки» объекта:

```js
let person = {
    name: "Leonardo",
    profession: {
        name: "developer"
    }
};
Object.freeze(person); // делает объект иммутабельным
person.profession.name = "doctor";
console.log(person); //вывод { name: 'Leonardo', profession: { name: 'doctor' } }
```

Вот — «глубокая заморозка»:

```js
function deepFreeze(object) {
    let propNames = Object.getOwnPropertyNames(object);
    for (let name of propNames) {
        let value = object[name];
        object[name] = value && typeof value === "object" ?
            deepFreeze(value) : value;
    }
    return Object.freeze(object);
}
let person = {
    name: "Leonardo",
    profession: {
        name: "developer"
    }
};
deepFreeze(person);
person.profession.name = "doctor"; // TypeError: Cannot assign to read only property 'name' of object
```

Сообщение об ошибке выводится лишь в строгом режиме. В обычном режиме значение не меняется без вывода сообщений об ошибках.

### <a name="30"></a> Почему JavaScript-программисты испытывают проблемы при использовании ключевого слова this?

Самое важное, что нужно понять о `this`, заключается в том, что у функций нет фиксированного значения `this`. Это значение зависит от того, как именно вызывается функция. Если мы говорим о том, что функция вызывается с некоторым конкретным значением `this`, это значит, что это значение определяется не во время объявления функции, а во время её вызова. Вот некоторые особенности `this`:

- Если функция вызывается в обычном виде (то есть, с использованием конструкции вида `someFunc()`), то `this` будет ссылаться на глобальный объект (в браузере это `window`). Если код выполняется в строгом режиме, то в `this` будет записано значение `undefined`.
- Если функция вызывается как метод объекта, то ключевое слово this будет представлено объектом, которому принадлежит метод.
- Если функцию вызывают с использованием `call` или `apply`, this будет представлено тем, что указано в качестве первого аргумента `call` или `apply`.
- Если функция вызывается в виде обработчика события, то в `this` будет целевой элемент события.
- Если функцию вызывают в виде конструктора, с использованием ключевого слова new, то в `this` будет новый объект, прототип которого установлен в качестве свойства `prototype` функции-конструктора.
- Если функция создана с использованием метода `bind`, то ключевое слово `this` функции будет жёстко привязано к значению, переданному bind в качестве первого аргумента. Это — единственное исключение из правила, в соответствии с которым функции не имеют жёстко заданного значения `this`. Функции, созданные с использованием `bind`, имеют иммутабельное значение `this`.

### <a name="31"></a> Сравните использование конструкции async/await и генераторов для реализации одного и того же функционала

- При итерировании генератора с использованием метода `.next()` каждый вызов этого метода приводит к возврату одного значения с помощью ключевого слова `yield`. При использовании конструкции async/await await-выражения выполняются последовательно.
Конструкция `async/await` упрощает реализацию определённого сценария использования генераторов.
- Значения, возвращаемые генератором, всегда имеют вид `{value: X, done: Boolean}`, а асинхронные функции возвращают промисы, разрешаемые со значением X, либо завершаются с ошибкой.
- Асинхронную функцию можно преобразовать в генератор, использующий промисы. Ниже приведён пример такого преобразования.

Вот асинхронная функция:

```js
// Асинхронная функция
async function init() {
    const res1 = await doTask1();
    console.log(res1);

    const res2 = await doTask2(res1);
    console.log(res2);

    const res3 = await doTask3(res2);
    console.log(res3);

    return res3;
}

init();
```

Вот аналогичный генератор.

```js
// Эта функция выполняет генератор
function runner(genFn) {
    const itr = genFn();

    function run(arg) {
        let result = itr.next(arg);

        if (result.done) {
            return result.value;
        } else {
            return Promise.resolve(result.value).then(run);
        }
    }

    return run;
}

// Вызывает функцию runner с передачей ей генератора
runner(function* () {
    const res1 = await doTask1();
    console.log(res1);

    const res2 = await doTask2(res1);
    console.log(res2);

    const res3 = await doTask3(res2);
    console.log(res3);

    return res3;
});
```

### <a name="32"></a> Напишите функцию сложения вида add(num1)(num2).

В оригинале это задача решается таким образом:

```js
const add = (a) => {
  let sum = a;
  
  const func = (b) => {
    if (b) {
      sum += b;
      return func;
    } 
    
    return sum;
  };
  
  return func;
};

add(2)(3)(); // 5;
```

Но потом вам ставят одно условие.

> Убрать в конце лишние скобки

```js
add(2)(3) // 5
add(1)(2)(5) // 8
```

Теперь задача усложнилась. А решение кроется в переопределении метода valueOf .

```js
const add = (a) => {
  let sum = a;
  
  const func = (b) => {
    sum += b;
    return func;
  };
  
  func.valueOf = () => sum;
  
  return func;
};

console.log(add(2)(3)); // 5;
```

Когда мы вызываем console.log , он ожидает увидеть String, если его там нет, то он попытается сделать из полученного значения String.
В примере выше после выполнения add(2)(3) возвращается function, которую console.log будет превращать в String, в ходе этих действий будет вызван метод valueOf для преобразования function к примитиву, а так мы переопределили данный метод, то он вернёт наше значение sum вместо стандартного.

### <a name="33"></a> Что выведется в консоль ? Объясните почему.

```js
let a = {};
let b = {key:'b'};
let c = {key:'c'};

a[b] = 123;
a[c] = 456;

console.log(a[b]);
```

Что же происходит? Когда у объекта устанавливается новое свойство, то JavaScript неявно сделает `stringify` значения. В коде выше b и c являются объектами, следовательно они оба конвертируются в `"[object Object]"` (String). Так как `stringify` значения равны, то получается, что мы присваиваем новое значение одному и тому же свойству.

__Ответ:__ 456

Равносильно, что написать:

```js
let a = {};
let b = 'object';
let c = 'object';

a[b] = 123;
a[c] = 456;
```
---

## :older_man: <a name="epilogue"></a> Послесловие

Само собой, что универсального «рецепта», как успешно пройти собеседование, не существует. Кто-то не сумеет пройти собеседование просто потому, что найдется более опытный соискатель с нужным набором знаний. В некоторых случаях причиной отказа становятся личные симпатии или антипатии руководства, и с этим вы ничего не сможете поделать. Но все же, правильная подготовка к собеседованию значительно повысит ваши шансы на успех.

Собеседование – это, прежде всего, личное общение с потенциальным работодателем. Ваше резюме уже изучили и заинтересовались. Скорей всего, вы также успешно прошли этап тестирования. Теперь с вами хотят встретиться и поговорить, составить о вас какое-то впечатление как о специалисте и человеке. Давайте разбираться, как подготовиться, чтобы это впечатление было как можно лучше.

### Запаситесь необходимыми знаниями

Относитесь к собеседованию как к своеобразному экзамену, отлично сдать который поможет хорошая теоретическая подготовка:

- **Изучите стандартный список вопросов ко всем кандидатам на трудоустройство и научитесь четко и быстро отвечать на них.**

Определите свои положительные качества и конкурентные преимущества, научитесь их подчеркивать при ответах на эти вопросы. Вам нужно уметь грамотно и развернуто, но без лишних слов сообщать о том, почему ваш выбор пал на эту компанию, почему вы покидаете предыдущее место работы, чего ждете от новой работы и на какие перспективы рассчитываете в будущем.

- **Проведите своеобразную «разведку», изучив направление и масштабы деятельности фирмы.**

Ознакомьтесь с уже запущенными и действующими проектами. Базируясь на этой информации, продумайте, какие еще вопросы могут к вам возникнуть: приходилось ли вам работать с определенным фреймворком или библиотекой, насколько хорошо вы знаете конкретные языки программирования, занимались ли разработкой схожих продуктов.

- **Найдите в интернете стандартные логические вопросы и задания, которые часто используют HR-менеджеры, и проработайте их.**

Такие задачи ставят перед соискателями не всегда, но за хорошую вакансию с большим конкурсом среди претендентов придется побороться.

### Проверьте грамотность и логичность своих резюме и тестового задания

Работодатель при собеседовании в первую очередь будут опираться на информацию в вашем резюме и результаты выполнения тестового задания. И обязательно проверит, соответствуют ли они реальному уровню ваших знаний и навыков.

Правильно составленное резюме – залог того, что вы, как минимум, привлечете внимание и работодатель выделит вас среди других соискателей. Но не стоит включать в него ложные сведения или оставлять явные недосказанности – это может поставить вас в неловкую ситуацию во время личного собеседования.

Тщательно и придирчиво перечитайте свое резюме, обратив особое внимание на перечисленные умения и выполненные проекты. Подумайте, какие вопросы по этому поводу могут возникнуть у менеджеров по персоналу или технических специалистов.

### Совершенствуйтесь

Нет идеальных специалистов, в том числе и среди программистов. Технологии совершенствуются настолько быстро, что даже самый продвинутый специалист имеет пробелы в знаниях. Но нередко отсутствие определенных знаний и навыков связано с личностными факторами. Это может быть банальная лень, отсутствие стремления к развитию, нежелание выходить за рамки своих узких профессиональных задач.

В результате подобного отношения к профессии вы можете не найти ответа на каверзный вопрос во время собеседования. И оправдания в духе «у меня не было нужды этим заниматься», «давно с этим не работал» вполне могут лишить вас возможности устроиться на место своей мечты. Поэтому при работе над предыдущим пунктом не тешьте себя иллюзиями, а честно определите и восполните свои пробелы в знаниях.

### Составьте речь

Этот совет особенно важен для тех, кто сильно волнуется или может растеряться в стрессовой ситуации. Заблаговременно составьте и заучите свое вступительное слово. Длина речи должна быть небольшой – около минуты. При этом вы должны суметь рассказать о себе как можно больше:

- 10-секундный рассказ о ваших человеческих свойствах и качествах;
- 30-секундное повествование о ваших профессиональных достоинствах;
- 10-секундный анонс ваших ожиданий от будущей работы;
- 10-секундная демонстрация знаний о потенциальном месте работы.

Все эти сведения зафиксируйте письменно, затем перемешайте так, чтобы сухая констатация фактов стала похожа на живое непосредственное общение, и озвучьте эту речь в начале собеседования. Если в эту минуту вы сможете сконцентрировать внимание на себе, то и волнение переборете, и позитивное впечатление создадите.

### Не молчите при решении задач

Как известно, обычные люди мысли читать не умеют. Ваши собеседники не в состоянии догадаться, как и о чем вы думаете. Ваше молчание – знак того, что решения у вас нет.

Не замыкайтесь в себе – проговаривайте все этапы размышлений над задачей. Это поможет вашему визави понять ход ваших мыслей и при необходимости направить вас в нужном направлении. Так самые простые коммуникативные навыки сослужат вам добрую службу, и вы получите желанную работу.

И последний, самый важный совет: __не впадайте в отчаяние из-за возможного отказа или неудачи на собеседовании__. Всем понравиться невозможно. И даже если вам откажут, стоит принять это как ценный опыт. Он обязательно пригодится вам в дальнейшем, когда вы будете готовиться к следующему интервью.
