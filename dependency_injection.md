# Injeção de dependencia


## Sem injeção de dependencia
```javascript
var service = function() {
    return { name: 'Service' };
}

var router = function() {
    return { name: 'Router' };
}

var doSomething = function(other) {
    var s = service();
    var r = router();
};

```

## Com injeção de dependencia
```javascript
var service = function() {
    return { name: 'Service' };
}

var router = function() {
    return { name: 'Router' };
}

var doSomething = function(service, router, other) {
    var s = service();
    var r = router();
};
```


# Bibliotecas que lidam com isso

* http://requirejs.org/
