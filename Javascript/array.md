# array - in javascript

<br>

## GET

```js
array[index]; // -> value
```

<br>

## SET

```js
array[index] = value; // atribuit / suprascris valoare
```

<br>

## Append element

Adaugat element la urma in array

`array.push(value);`

### Exemplu: Construit array coloana

```js
var numeAdaugate = [];

produseAdaugate.forEach(produsDeAdaugat => {
// produseAdaugat = [paine, orez, ovaz]

numeAdaugate.push([produsDeAdaugat]); // pt a adauga produsele noi la ingrediente
}

```

<br>

## Remove - primul element
Sters 1 element pornind de la index

```js
arr.splice(index, 1); 
```

Exemplu: `array.splice(0, 1);` va sterge primul element din array

> [!NOTE]
> `array.splice(0, 1);`
> - sterge primul element
> - muta tot arrayul la stanga
> - returneaza un nou array, cu elementele sterse

<br>

## array length

```js
array.length; // array length
```

<br>

## are element

```js
if( array.includes('banana') ){ // true / false
    // code
}
```

![array](/Javascript/_img/map%20VS%20array%20-%20javascript.png)

<br>

## destructuring

E foarte utila pt descarcat continut array -> in mai multe variabile simultan

```js
const [nume, cantitate] = ["banana", 100];
```

> [!NOTE]
> in Python este `mytext, mynumber = ["banana", 100];`

<br>

## copiat array (intr-o noua variabila)

> [!CAUTION]
> In python cand copiezi un array, devine o alta entitate, insa in javascript `var myNewArray = myOldArray` este de fapt un pointer

Pentru a copia un array in javascript:

```js
var newArray = [...Array]; //spreading operator
```

<br>

## filtrare array

`array.filter()`

```js
// filtrare daca nume sau valoare sunt goale
const filteredValues = values.filter(row => {
    const name = row[0];
    const value = row[1];
    
    if(name != "" && value != ""){
        return true; // cele care sunt true sunt pastrate
    }
    else {
        return false; // cele care sunt false sunt skip
    }
});
```

> [!IMPORTANT]
> Aceasta filtreaza array, si returneaza un nou array, cu o lungime mai mica.

> [!CAUTION]
> nu poti amesteca `array.filter()` cu `throw new error()`. Validarea datelor se face separat fata de filtrare, altfel scriptul se va oprii din aceasta cauza

![array.filter + array.map](/Javascript/_img/array_map%20si%20array_filter.png)

<br>

## transformare continut array (2d-array)

`array.map()`

```js
const numbers = [1, 2, 3];

const doubles = numbers.map(n => n * 2); // returns [2, 4, 6]
```

> [!IMPORTANT]
> returneaza un nou array, cu continut modificat


> [!WARNING]
> in `map()` nu se modifica lungimea array-ului, ci doar continutul acestuia. Pt aceasta  se foloseste functia `filter()` de mai sus


> [!NOTE]
> Pot face calculul direct in *2D-Array*, fara sa mai fie nevoie sa-l transform in *hashmap*, si apoi la loc.
> La SET valoare se poate face direct in *2D-Array*. insa la GET valoare este nevoie de *hasmap*, pt a extrage rapid valoarea

<br>
