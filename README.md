# wediki-data

Data for <https://wediki.herokuapp.com>

## Installation

### Requirements

## Usage

### wediki files (*.wdk)

`<md>` defines the start of a markdown segment. It makes up the skeleton of the page. In the markdown segment you define the structure in normal markdown manner
`</md>` defines the end of a markdown segment

`<js>` defines the start of a javascript segment. In here you can either run simple javascript commands (such as alerts, confirms, prompts), but also define (populate) the tables you are refering to from the markdown segment. Special Rules apply here.
`</js>` defines the end of a javascript segment

#### Syntax-Highlighted (Coloured) Multi-Line Code-Blocks

[shiki languages](https://github.com/shikijs/shiki/blob/master/docs/languages.md) apply in a normal markdown way, e.g.

```csharp
```csharp // will highlight the block as shiki would highlight C# code
```

#### Special Rules

##### Tables

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

###### ASYNC

when using async operations (the "await"-operator), the "tables"-variable shan't be overwritten! Thus, instead of using `tables = [table1, table2]`, use something like `tables.push(table1); tables.push(table2);`

#### HTTP-Requests

*custom headers / parameters are not supported in our wrappers, obviously you can do the requests yourself as well*

If you want to execute http requests, then that's no problem!
Simply use our wrappers:

```javascript
return request.async.get.plain('https://jsonplaceholder.typicode.com/todos/1').then(plain => { }); // asynchronously requests and continues with raw/plain text
return request.async.get.json('https://jsonplaceholder.typicode.com/todos/1').then(json => { }); // asynchronously requests and continues with JSON object

request.sync.get.plain('https://jsonplaceholder.typicode.com/todos/1'); // synchronously requests and returns as raw/plain text
request.sync.get.json('https://jsonplaceholder.typicode.com/todos/1'); // synchronously requests and returns as JSON object
```

### router.json

Currently hardcoded to Formulas and Wiki, subitems are fully customisable and dynamic.
Icon is optional, and can be set to either:

1. any of the [creative-tim x nucleoApp icons](https://demos.creative-tim.com/vue-black-dashboard/#/icons) e.g. `icon-atom`
2. any of the [free Font Awesome icons](https://fontawesome.com/icons?m=free) e.g. `far fa-keyboard`
3. any svg (note: must still be a valid json object, i.e. replace " with ') e.g. from [google](https://fonts.google.com/icons/) or [HeroIcons](https://heroicons.dev/) (you might need to set fill="white" in some paths)
4. select presets are available:
   1. $HOME
   2. $CODE
   3. $FORMULA | $MATHS | $MATH
   4. $TERMINAL
   5. $BOOK | $WIKI
   6. $DASHBOARD
   7. $CHEMISTRY
   8. $SETTINGS
   9. $ADJUSTMENTS
   10. $CHAT
   11. $CHIP
   12. $CLIPBOARD
   13. $CLOUD
   14. $TRENDING
   15. $API
   16. $DONE
   17. $SCHOOL
   18. $COMMENT | $COMMENTS
   19. $DESIGN
   20. $IMAGE | $PHOTO
   21. $IMPORT | $EXPORT | $IMPORTEXPORT | $IMPORT&EXPORT | $IMPORT-EXPORT
   22. $SPLIT
   23. $MERGE
   24. $LINK
   25. $SYNC | $SYNCHRONISE | $SYNCHRONIZE | $RELOAD | $REFRESH
5. if the icon key is not described (null or undefined), `icon-atom` is taken by default

## Support

Create an issue on GitHub: <https://github.com/llnulldisk/wediki-data/issues>

## Roadmap

## Contributing

## Authors and acknowledgment

- [dxstiny](https://github.com/dxstiny)
- [llnulldisk](https://github.com/llnulldisk)

## License

```text
claythve.rf.gd
Copyright (C) 2022  llnulldisk

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```
