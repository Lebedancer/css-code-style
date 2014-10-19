# Css style guide (Alpha)

## <a name='ids'>Id's</a>
Не использовать id (\#) при написании стилей!!!

```css
    // плохо
    #page-header {}
    
    // хорошо
    header {}
    
    // хорошо
    [aria-role=header] {}
    
    // хорошо
    .page-header {}
```
