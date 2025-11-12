# Tehnici de programare

## Validare date - Verificare duplicate *true* in array 

> [!NOTE]
> Pt validare date, o functie este cea mai buna solutie, pt ca:
> - poti vedea mai bine structura codului
> - cand se repeta validarea (ex. supa, mancare, desert)

<br>

### Strategie iesire rapida din loop

Cea mai rapida varianta de verificare este una care poate finaliza loop-ul imediat ce are informatia (premeditat)

```js
for (const value of arr) {
    if (value === true) {
      trueCount++;
      if (trueCount >= 2) {
        return true; // Found multiple 'true' values, stop immediately
      }
    }
}
```

### Strategie verificare casute bifate

```js
var gasit = 0;
var supa_selectata; // la fel si pt supa, si pt mancare, si pt desert;
var index;

for(let item=0; item < array_casute_supa.length; item++){
  if(array_casute_supa[item] && gasit == 1){
    gasit++; //gasit=2
    break;
  }
  if(array_casute_supa[item]){
    gasit++; // gasit=1
    supa_selectata = selectare_matrice_supa[item][2];
    index = item; // pt a putea prelua denumirea casutei bifate
  }
}
```

<br>

## Convert - 2D Array -> Array-Objects

```js
// 1. Extract the header row (keys)
const headers = data[0];
  
// 2. Extract the data rows (excluding the header)
const rows = data.slice(1);

// 3. Map each row to an object
const hashmap = rows.map(row => {
    const obj = {};

    headers.forEach((header, index) => {

      // Use the header text as the key and the row cell value as the value
      obj[header] = row[index];
    });

    return obj;
});
```

> [!NOTE]
> Acesta returneaza un array de obiecte

<br>

## Convert - Array-Objects -> 2D Array

```js
// 1. Get the header row (keys) from the first object
const headers = Object.keys(hashmap[0]);

// 2. Map each object to an array of its values, in the header order
const dataRows = hashmap.map(obj => {
    return headers.map(header => obj[header]);
});
  
// 3. Combine the header row and the data rows
var results = [headers, ...dataRows];
```

> [!NOTE]
> `Object.keys(hashmap[0]);` este punctul cheie pt ca extrage numarul de coloane, prin care apoi se itereaza cu `map()`

<br>

## Extract a big-area (2D-Array) & filtrare

1. Extras big area din google sheet

Identify the first column (A) and the last column (F) and get all the data in one block `(A1:F10)`.

2. Filtrat coloanele care ma intereseaza

Column A -> Index 0
Column C -> Index 2
Column F -> Index 5

A. Filtrat 1 singura coloana

```js
const columnIndex = 1; // 0 for "paine", 1 for "100", 2 for "Kg"

const quantitiesArray = twoDArray.map(row => row[columnIndex]);
```

B. Filtrat mai multe coloane

```js
const COL_INDICES = [0, 2, 5];

// Map over the rows to extract only the needed columns
const filteredData = twoDArray.map(row => {

// For each 'row' (inner array), map over the desired indices
return COL_INDICES.map(colIndex => row[colIndex]);

});
```

<br>

## conversie - hashmap -> 2D-Array

1. Daca hashMap-ul are *key*: *valoare*

```js
  total = Array.from(Stoc);
  // [["paine", 200.0], ["ceapa", 100.0]]
```

2. Daca hashMap-ul are *key*: [valoare1, valoare2] , sau mai multe valori

```js
// Stoc Map Structure: { "paine" => [200.0, "kg"], "ceapa" => [100.0, "kg"] }

var total = Array.from(Stoc.entries(), entry => {
    const productName = entry[0]; // the key
    const [quantity, unit] = entry[1]; // the value (destructured array)

    return [productName, quantity, unit];
});

// [["paine", 200.0, "kg"], ["ceapa", 100.0, "kg"]]
```

> [!NOTE]
> Se foloseste `Array.from()` pt conversie, iar continutul se poate modifica inauntru
> `map.entries()` -> array of keys

<br>

## Conversie - hashmap.keys -> array

Extragi doar denumirea cheilor si faci un array cu acestea

```js
// 1. Use .keys() to get the iterator
// 2. Use Array.from() to convert the iterator to an array
var keysArray = Array.from(myMap.keys());

Logger.log(keysArray); 
// Output: [paine, orez, miere]
```

<br>

## Conversie - Array -> 2D-Array (tip coloana)

```js
// stockQuantities is a 1D array: [100, 50, 25]

// Use map to wrap each item in its own array:
var oneColumnArray = stockQuantities.map(value => [value]);

// Output: [[100], [50], [25]]
```