# wediki: data

## wediki (*.wdk) files
md defines the start of a markdown segment. It makes up the skeleton of the page. In the markdown segment you define the structure in normal markdown manner

/md defines the end of a markdown segment

js defines the start of a javascript segment. In here you can either run simple javascript commands (such as alerts, confirms, prompts), but also define (populate) the tables you are refering to from the markdown segment. Special Rules apply here.

/js defines the end of a javascript segment

#### Syntax-Highlighted (Coloured) Multi-Line Code-Blocks
[shiki languages](https://github.com/shikijs/shiki/blob/master/docs/languages.md) apply in a normal markdown way, e.g.

```csharp
```csharp // will highlight the block as shiki would highlight C# code
```

### Special Rules
#### Tables
Placeholders:
$T${TABLE_NAME}
Population:
simply write to the "tables" variable (DO NOT INITIALISE / DECLARE IT! It is being set for the code already)
example table:

```js
{
  title: "Homework", // this would be {{TABLE_NAME}}
  columns: ["subject", "homework"],
  data: [{subject: "Maths", homework: "page 1-10"}]
}
```

##### ASYNC
when using async operations (the "await"-operator), the "tables"-variable shan't be overwritten! Thus, instead of using `tables = [table1, table2]`, use something like `tables.push(table1); tables.push(table2);`

### HTTP-Requests
*custom headers / parameters are not supported in our wrappers, obviously you can do the requests yourself aswell*

If you want to execute http requests, then that's no problem!
Simply use our wrappers:

```javascript
await request.async.get.plain('https://jsonplaceholder.typicode.com/todos/1'); // asynchronously requests and returns as raw/plain text
await request.async.get.json('https://jsonplaceholder.typicode.com/todos/1'); // asynchronously requests and returns as JSON object

request.sync.get.plain('https://jsonplaceholder.typicode.com/todos/1'); // synchronously requests and returns as raw/plain text
request.sync.get.json('https://jsonplaceholder.typicode.com/todos/1'); // synchronously requests and returns as JSON object
```

## License
    wediki-data
    Copyright (C) 2021 dxstiny and Claythve

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.
