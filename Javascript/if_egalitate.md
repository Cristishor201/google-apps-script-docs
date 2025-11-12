# Tipuri de egalitate - in javascript

## Egalitate stricta

Checks: **Value** AND **Type**.

Type Coercion: NO. It will *not attempt to convert types* before comparing.

```js
null === undefined;  // false
```

![egalitate stricta](/Javascript/_img/strict%20equality.png)

## Egalitate aproximata

Checks: **Value** only (after potential conversion).

Type Coercion: YES. If the operands are of different types, JavaScript will try to *convert one or both of them to a common type* (usually a Number) before comparing the values.

```js
null == undefined;   // true
```

```js
if (myVariable == null) {
    // runs if myVariable is null OR undefined.
}
```


![egalitate aprox](/Javascript/_img/loose%20equality.png)

> [!NOTE]
> Desi este deprecated, e foarte utila cand ai de verificat cifre preluate ca text din google sheet, sau in conditii similare