# Temporal Dead Zone Examples
Repository containing examples of Temporal Dead Zone 

The blog article can be found at <a href=http://tsshriram.com/2016/01/19/the-mysterious-temporal-dead-zone/>The Mysterious Temporal Dead Zone</a>

#Example 1

```
var countMethod(){
console.log(count); //reference error
};

countMethod();
let count;
```

#Example 2

```
let count = 100;
console.log(count); //prints 100

(
function(){
console.log(count);//reference error
let count = 100;
})();
```

#Example 3

```
function getAddedValue(firstArgument,secondArgument, thirdArgument=3) {
     console.log(firstArgument+secondArgument+thirdArgument);

}

getAddedValue(1,2); // 6
```

#Example 4

```
function getAddedValue(firstArgument=secondArgument,secondArgument) {
     console.log(firstArgument+secondArgument);
}

getAddedValue(1); //reference error
```

#Example 5

```
if (true) {
    console.log(typeof definedVariable); // ReferenceError (TDZ)
    console.log(typeof undefinedVariable); //undefined - this variable is not defined
    let definedVariable;
}
```

#Example 6

```
function getAddedValue(firstArgument = secondArgument, secondArgument) {
    return firstArgument + secondArgument;
}

console.log(getAddedValue(1, 1));         // 2
console.log(getAddedValue(undefined, 1)); // throws error
```
