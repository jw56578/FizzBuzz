# FizzBuzz
different ways to do this thing

##No conditionals

```

var func = null;
var conditions = {
    1:{true:null,
       false:function(i){
           return function(){console.log(i)};
       }},
    3:{true:function(){
        return func;
    },false:function(){
    return function(){console.log('fizz')};
    }},
    5:{true:function(){ return func;},false:function(){
        return function(){console.log('buzz')};
    }},
    15:{true:function(){ return func;},false:function(){
        return function(){console.log('fizzbuzz')};
    }}
                 
}
var l = 100;
var words = [];
for(l = 1 ; l < 100 ; l ++){    
    for(var thing in conditions){
        var result = l % thing;
        func = conditions[thing][!!result](l);
    }
    func();
}
```
