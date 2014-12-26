# Css style guide (Alpha)

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

## <a name='ids'>Наименование</a>
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

## <a name='ids'>проблемы/табы</a>

## <a name='ids'>префиксы/табы</a>

## <a name='ids'>многострочные</a>

## <a name='ids'>Цвета</a>
Цвета объявляются исключительно в hex формате. 3-6 символов, не важно. Регистр - не важен.
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


## <a name='ids'>Selectors</a>
Selectors should be on a single line, with a space after the last selector, followed by an opening brace. A selector block should end with a closing curly brace that is unindented and on a separate line. A blank line should be placed between each selector block. Selectors should never be indented.

```selector {
   }
   
   selector {
   }
   ```
   
   Multiple selectors should each be on a single line, with no space after each comma.
 ```  
   selector1,
   selector2,
   selector3,
   selector4 {
   }
   ```
## <a name='ids'>велчины</a>
When denoting the dimensions — that is, the width or height — of an element or its margins, borders, or padding, specify the units in either em, px, or %. If the value of the width or height is 0, do not specify units.
```
width: 12px;  /* Okay */
  width: 12%;   /* Okay */
  width: 12em;  /* Okay */
  width: 12rem; /* Okay */
  width: 0;     /* Okay */
  width: 12;    /* Not okay */
  width: 0px;   /* Not okay */
  ```