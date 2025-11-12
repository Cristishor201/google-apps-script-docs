# for loops - diferente

## for

```js
fo (let i=0; i < n; i++){
    console.log(array[i]); // afisat in consola element array
}
```
<br>

## forEach

```js
array.forEach( (item, index, fullArray) => {
    console.log(item); // afisat in consola element array
});
```

> [!IMPORTANT]
> forEach nu are `break` / `continue`


> [!NOTE]
> `forEach` este folosit pt a schimba continut, insa nu retunreaza nimic

<br>

## for..of

- este modern JS

```js
for(element of array){
    console.log(element); // afisat in consola element array
}
```

> [!NOTE]
> `for..of` are ambele capacitati de forma scurta ca la `forEach` si poti folosi `break` / `continue`
> Este un mare avantaj, pt ca codul este mai clean, si nu ai un *index* sau *i* in plus pt a accesa continutul

![for..of - forEach](/Javascript/_img/for_of%20VS%20foreach.png)