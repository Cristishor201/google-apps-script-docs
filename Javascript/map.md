# map (hashmap / dictionary)

## GET

```js
map.get(key); // -> value
```

## SET

```js
map.set(key, value); // adauga new value, sau suprascrie una existenta 
```

> [!NOTE]
> modern JavaScript HashMap, mentine ordinea de insertie in hashmap

## daca are un element

```js
if( map.has("banana") ){ // true | false
    //code
}
```

![map - array](/Javascript/_img/map%20VS%20array%20-%20javascript.png)

## map - length

```js
map.size; // 3
```


## GET al doilea element din array valoare

```js
// Get the iterator of values, convert to an array, and then map to get the second element
let secondValues = Array.from(Stoc.values()).map(innerArray => innerArray[1]);
```