# Css style guide (Beta)
## <a name='tableOfContents'>Оглавление</a>
1. [Id's](#ids)
1. [Наименование селекторов](#selectorsName)
1. [Структура селектора](#selectorStructure)
1. [Свойство-значение](#rule)
1. [Структура пары свойство-значение](#ruleStructure)
1. [Контроллы, компоненты, js](#controlsAndJs)
1. [Отступы и пробелы](#whitespaces)
1. [!important](#important)
1. [Структура препроцессора(less/sass)](#preprocessor)


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

## <a name='selectorsName'>Наименование селекторов</a>
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

- Названия классов должны быть абстрактны и выражать смысловое нежели визуальное значение.
```
    // плохо
    .greenButton {}

    // хорошо
    .successButton {}
```


## <a name='selectorStructure'>Структура селектора</a>
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

## <a name='rule'>Свойство-значение</a>
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

## <a name='ruleStructure'>Структура пары свойство-значение</a>
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

## <a name='controlsAndJs'>Контроллы, компоненты, js</a>
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

## <a name='whitespaces'>Отступы и пробелы</a>
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

## <a name='important'>!important</a>
Использовать !important можно только в стилях ядра, для вещей которые никогда не должны быть переопределены.
```
    // плохо
    .table{
        width: 100% !important;
    }

    // хорошо
    .error{
        color: red !important;
    }
```

## <a name='preprocessor'>Структура препроцессора(less/sass)</a>
- Переменные пишутся сamelCase'ом.
Глобальные переменные(используются более чем в одном файле) пишутся с большой буквы.
Локальные(используется внутри одного файла) пишутся с маленькой.
```
    @Global;
    @local;
```

- Вложеннные селекторы отбиваются 4 пробелами.
```
    // плохо
    .table{
    ∙∙tr {
        width: 100% !important;
      }
    }

    // хорошо
    .table{
    ∙∙∙∙tr {
            width: 100% !important;
        }
    }
```

- Избегайте неоправданной вложенности.
```
    // плохо
    .table{
        tbody {
            tr {
                td {
                    .button{}
                }
            }
        }
    }

    // хорошо
    .table .button{}
```

- Используйте вложенность для похожих селекторов.
```
    // плохо
    .table > thead > tr > th {}
    .table > thead > tr > td {}

    // хорошо
    .table > thead > tr {
      > th { }
      > td { }
    }
```

- Общие цвета, размеры и прочие хаарактеристики следует присваивать переменным.

```
    // плохо
    .error { color: #CB3338; }
    .closeLink { background: #CB3338; }

    // хорошо
    @redColor: #CB3338;
    .error { color: @redColor; }
    .closeLink { background: @redColor; }
```

- Для однотипных кусков свойств целесообразно использовать миксины.
```
    // плохо
    .block {
        -webkit-box-shadow: none;
        box-shadow: none;
    }

    // хорошо
    .box-shadow(@shadow) {
      -webkit-box-shadow: @shadow;
      box-shadow: @shadow;
    }

    .block {
        .box-shadow(none);
    }
```