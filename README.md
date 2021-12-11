# sql-select-utils

A js library for displaying arrays of objects in tabular format.
Utilities for working with sql-select npm library.

## Install

```sh
npm install sql-select-utils
```

## Usage

```javascript
import { drawTable } from 'sql-select-utils'

const input = [
    { name: 'John', salary: 20 },
    { name: 'James', salary: 30 },
    { name: 'Joe', salary: 50 },
]

// without config object
console.log(drawTable(input))
/*
+-------+--------+
| name  | salary |
+-------+--------+
| John  |     20 |
| James |     30 |
| Joe   |     50 |
+-------+--------+
3 rows selected
*/
```

```javascript
import { drawTable } from 'sql-select-utils'

const input = [
    { name: 'John', salary: 20 },
    { name: 'James', salary: 30 },
    { name: 'Longname', salary: 50 },
]

// with config object => max width of column 1
console.log(drawTable(input, { 1: 5 }))
/*
+-------+--------+
| name  | salary |
+-------+--------+
| John  |     20 |
| James |     30 |
| Longn |     50 |
+-------+--------+
3 rows selected
*/
```

```javascript
import { htmlTable } from 'sql-select-utils'

const input = [
    { name: 'John', salary: 20 },
    { name: 'James', salary: 30 },
    { name: 'Joe', salary: 50 },
]

// without config object
console.log(htmlTable(input))
/*
<table>
    <thead>
        <tr>
            <th scope="col">name</th>
            <th scope="col">salary</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>John</td>
            <td>20</td>
        </tr>
        <tr>
            <td>James</td>
            <td>30</td>
        </tr>
        <tr>
            <td>Joe</td>
            <td>50</td>
        </tr>
    </tbody>
</table>
*/
```

```javascript
import { htmlTable } from 'sql-select-utils'

const input = [
    { name: 'John', salary: 20 },
    { name: 'James', salary: 30 },
    { name: 'Joe', salary: 50 },
]

// with config object => caption, class
// both properties are optional
console.log(htmlTable(input, { caption: 'employees', class: true }))
/*
<table>
    <caption>employees</caption>
    <thead>
        <tr>
            <th scope="col" class="item-name">name</th>
            <th scope="col" class="item-salary">salary</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="item-name">John</td>
            <td class="item-salary">20</td>
        </tr>
        <tr>
            <td class="item-name">James</td>
            <td class="item-salary">30</td>
        </tr>
        <tr>
            <td class="item-name">Joe</td>
            <td class="item-salary">50</td>
        </tr>
    </tbody>
</table>
*/
```




