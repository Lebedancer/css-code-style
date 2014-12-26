# Css style guide (Beta)

## <a name='ids'>Id's</a>
Не использовать id (\#) при написании стилей!!! Никогда, даже если не в моготу.
```
    // плохо
    #page-header {}
    
    // хорошо
    header {}
    
    // хорошо
    [aria-role=header] {}
    
    // хорошо
    .pageHeader {}
```

## <a name='ids'>Наименование селекторов</a>
- Основная часть класса именуется в стиле lowerCamelCase.
```
    // плохо
    .BadClass {}

    // плохо
    .bad-class {}

    // плохо
    .bad_class {}

    // хорошо
    .goodClass {}
```

- Названия классов должны быть корокими насколько возможно, но не терять при этом смысл.
```
    // плохо(слишком длинный)
    .buttonWhichUseToOpenDialog {}

    // плохо(не ясен смысл)
    .atr {}

    // плохо(избыточный)
    .navigation {}

    // хорошо
    .author {}
    .nav {}
```

- Не использвать теги в связке с классами. Это делает их узкоспециализированными и снижает производительность.
```
    // плохо
    div.error {}

    // хорошо
    .error {}
```

- Названия клссов должны быть абстрактны и выражать смысловое нежели визуальное значение.
```
    // плохо
    .greenButton {}

    // хорошо
    .successButton {}
```


## <a name='ids'>Структура селектора</a>
Содержимое селектора оборачивается в фигурные скобки ({}).
```
    // плохо
    .selector
        display: block;

    // хорошо
    .selector {
        display: block;
    }
```

Открывающая фигурная скобка находится на той же строке, что и селектор.
```
    // плохо
    .selector
    {
        display: block;
    }

    // хорошо
    .selector {
        display: block;
    }
```

Множественные селекторы пишутся в столбец через запятую
```
    // плохо
    .selector1, .selector2, .selector3, .selector4 {
        display: block;
    }

    // хорошо
    .selector1,
    .selector2,
    .selector3,
    .selector4 {
        display: block;
    }
```

## <a name='ids'>Свойство-значение</a>
- Старайтесь использовать однострочную запись свойств вместо многострочной.
```
    // плохо
    padding-bottom: 2em;
    padding-left: 1em;
    padding-right: 1em;
    padding-top: 0;

    // хорошо
    padding: 0 1em 2em;
```

- Не ставьте единицы измерения после нулевых значений. Это бессмыслено, но занимает место.
```
    // плохо
    margin: 0px

    // хорошо
    margin: 0
```
- Цвета объявляются исключительно в hex формате. 3-6 символов, не важно. Регистр - не важен.
 Это связано с тем, что дизайнеры предоставляют цвета, именно в этом формате.
```
    // плохо
    color: red;

    // плохо
    color: rgb(58, 58, 58);

    // плохо
    color: rgba(58, 58, 58, 0);

    // плохо
    color: hsl(60,100%,25%);

    // хорошо
    color: #FFF;

    // хорошо
    color: #fe9848
```
- Используйте одинарные ('') вместо двойных("") ковычек.
```
    // плохо
    font-family: "open sans", arial, sans-serif;

    // хорошо
    font-family: 'open sans', arial, sans-serif;
```

## <a name='ids'>Структура пары свойство-значение</a>
Каждая пара свойство-значение должно заканчиваться точкой с запятой.
```
    //Плохо
    selector {
        name: value
    }

    //Хорошо
    selector {
        name: value;
    }
```

- **Многострочные**: Каждое свойство должно находиться на своей строке, начиная со строки после фигурной скобки.
Все свойства должны быть выровнены в один стобец.
```
    //Плохо
    selector {
    name: value;
        name: value;
    }

    //Плохо
    selector {    name: value;
        name: value;
    }

    // Хорошо
    selector {
        name: value;
        name: value;
    }
```

- **Селекторы с одним свойством**: Данные селекторы допускается писать в одну строку.
Свойство отбивается пробелами с обеих сторон.
```
    // Хорошо
    selector {
        name: value;
    }

     // Хорошо
    selector { name: value; }
```

## <a name='ids'>Контроллы, компоненты, js</a>
- **Классы для js**: Старайтесь не использовать в js в качестве селлекторов классы, которые влияют на верстку.
Если в js необходимо привязаться к какому-нибудь элементу по классу, то следует добавить элементу дополнительный класс
с префиксом js.
```
    // плохо
    $('.mdButton')

    // хорошо
    $('.js-saveButton')
```

- **Контроллы и компоненты**: Классы в компонентах и контроллах должны задаваться по БЭМ нотации.

## <a name='ids'>Отступы и пробелы</a>
- Селекторы не отбиваются ничем.
- Свойстава отбиваются 4 пробелами
```
    // плохо
    .selector {
    ∙∙display: block;
    }

    // плохо
    .selector {
    display: block;
    }

    // хорошо
    .selector {
    ∙∙∙∙display: block;
    }
```

- Между многострочными селекторами должна быть пустая строка.
```
    // плохо
    .selector{
        display: block;
        color: #fff;
    }
    .selector2{
        display: block;
        color: #fff;
    }

    // хорошо
    .selector{
        display: block;
        color: #fff;
    }

    .selector2{
        display: block;
        color: #fff;
    }
```

- Перед открывающейся фигурной скобкой ставится пробел.
```
    // плохо
    .selector{
        display: block;
    }

    // хорошо
    .selector {
        display: block;
    }
```

- Между свойством и значением ставится пробел.
```
    // плохо
    .selector{
        display:block;
    }

    // хорошо
    .selector {
        display: block;
    }
```
