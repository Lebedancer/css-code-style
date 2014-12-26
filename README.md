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
    .page-header {}
```

## <a name='ids'>Наименование</a>

- **Основная часть**: Основная часть класса именуется в стиле lowerCamelCase.

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

## <a name='ids'>Property-Value Pairs</a>
Property-value pairs should be listed starting on the line after the opening curly brace. Each pair should:

be on its own line;
be indented one level;
have a single space after the colon that separates the property name from the property value; and
end in a semicolon.

```
selector {
  name: value;
  name: value;
}
```


## <a name='ids'>проблемы/табы</a>

## <a name='ids'>префиксы/табы</a>

## <a name='ids'>многострочные</a>

## <a name='ids'>цвета</a>
color: #FFF;    /* Okay */
  color: #FE9848; /* Okay */
  color: #fff;    /* Not okay */


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