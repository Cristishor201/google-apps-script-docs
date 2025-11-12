# organizare proiect - Google Apps Script

## Detalii proiect

<ul>
    <li>poti avea acelasi nume de functie, in proiecte diferite</li>
    <li>o functie este accesibila in alt fisier, fara import (o functie e accesibila global in interiorul unui proiect)</li>
    <li>
        <details>
<summary> se poate folosi `class` in Google Apps Script:</summary>

```js
// Define a custom class
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    Logger.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

// Create an instance of the class
function createPerson() {
  const john = new Person("John Doe", 30);
  john.greet();
}
```

> [!NOTE]
> instanta unei `class` se defineste intr-o functie care se poate apela la un *buton* sau *event*

</details>
</li>
    <li>variabilele globale se declara inaintea primei functii dintr-un fisier</li>
    <li>The spreadsheet I/O (citire / scriere) este partea lenta. (nu un <code>foreach</code> loop)</li>
</ul>

## Atribuire script

Exemplu functie din interiorul unui fisier `Cantina.gs`

```js
function cantina() {
  // aici vine codul care rulează
  // ex: var sheet = SpreadsheetApp.getActiveSheet();
}
```

La atribuire script la un buton, vei trece : `cantina` , adica numele functiei.
Nu numele fisierului *.gs*.

## Checkboxes

Casutele de bifare din google sheet inregistreaza valoarea:
- la bifare -> `true`
- la debifare -> `false`

```js
const checkboxCell = sheet.getRange("A1");
const isChecked = checkboxCell.getValue(); // Returns true or false
```