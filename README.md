# nodejs-note

- [__dirname 与 process.cwd()](#__dirname 与 process.cwd())


## __dirname 与 process.cwd()区别

cwd() 是当前执行node命令时候的文件夹地址 
__dirname 是被执行的js 文件的地址

```js
Project 
├── main.js
└──lib
   └── script.js
```
main.js
```js
console.log(process.cwd())
// C:\Project
console.log(__dirname)
// C:\Project
console.log(__dirname===process.cwd())
// true
```
main.js
```js
require('./assets/script.js')
console.log(process.cwd())
// C:\Project
console.log(__dirname)
// C:\Project
console.log(__dirname===process.cwd())
// true
```
script.js
```js
console.log(process.cwd())
// C:\Project
console.log(__dirname)
// C:\Project\lib
console.log(__dirname===process.cwd())
// false
```
