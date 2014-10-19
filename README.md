# Css style guide <span style="color:red">Alpha</span>

## <a name='ids'>Id's</a>
Не использовать id (\#) при написании стилей!!!

```javascript
    // плохо
    #page-header {}
    
    // хорошо
    header {}
    
    // хорошо
    [aria-role=header] {}
    
    // хорошо
    .page-header {}
```