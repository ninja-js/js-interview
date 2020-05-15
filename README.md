<div align="center">
  <h1>Вопросы и ответы для собеседования Front-end/JS разработчика и не только</h1>
  <h5>Хотите подготовиться к собеседованию по JavaScript и ищете вопросы, на которых можно попрактиковаться? Если так — считайте, что ваши поиски окончены.</h5>
</div>

Мы собрали много вопросов по JavaScript, предназначенных для тех, кто хочет превратиться из джуниора в сеньора, для тех, кто стремится успешно пройти собеседование в сфере фронтенд-разработки и получить интересное предложение от работодателя.

## Содержание

0. [Послесловие](#epilogue)
1. [Какие навыки необходимо обязательно подтянуть для собеседования?](#wtf_skills)
2. [Объясните особенности проверки равенства значений в JavaScript.](#one)
3. [Приведите примеры приведения к логическому типу значений, не относящихся к этому типу](#two)
4. Что такое IIFE?
5. Когда следует использовать стрелочные функции, которые появились в ES6?
6. В чём разница между ES6-классами и конструкторами функций?
7. Расскажите о методе Function.prototype.bind().
8. Для чего обычно используются анонимные функции?
9. В чём разница между методом Object.freeze() и ключевым словом const?
10. Что такое «генератор»?
11. Когда стоит использовать генераторы?
12. Что такое «поднятие переменных»?
13. Что выведет следующий код?
14. Что такое всплытие событий?
15. Что такое перехват событий?
16. Можете ли вы объяснить каждую часть URL?
17. В чем разница между npm и npx?
18. Что такое WebAssembly?
19. Как работает CSS Flexbox?
20. Что такое AJAX и для чего он нужен?
21. Что такое JAMstack и как с ним работать?
22. Что такое «временная мёртвая зона» в ES6?
23. Можете ли вы описать основное различие методов массивов forEach () и map ()? В каких ситуациях вы предпочли бы один из этих методов другому?
24. Расскажите о шаблоне проектирования «Прототип»
25. Чем отличаются друг от друга необъявленная переменная, переменная, содержащая значение null, и undefined-переменная? Как проверить переменную на предмет того, что она необъявлена, а также на null и undefined?
26. Расскажите о шаблоне проектирования «Открытый модуль»
27. В чём разница между объектами Map и WeakMap?
28. Как в JavaScript-функции передаются параметры: по ссылке или по значению?
29. Как организовать «глубокую заморозку» объекта?
30. Почему JavaScript-программисты испытывают проблемы при использовании ключевого слова this?
32. Сравните использование конструкции async/await и генераторов для реализации одного и того же функционала.
33. [Напишите функцию сложения вида add(num1)(num2).](#33)
34. [Что выведется в консоль ? Объясните почему.](#34)
25. 

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

### <a name="34"></a> Что выведется в консоль ? Объясните почему.

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

### <a name="33"></a> Напишите функцию сложения вида add(num1)(num2).

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

---

## <a name="epilogue"></a> Послесловие

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
