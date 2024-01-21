# JavaScript 中的全部循环方法

## for 循环

```js
const arr = [1,2,3]
for (let i = 0; i < arr.length; i++) {
  console.log(i, arr[i])
}
// 0 1
// 1 2
// 2 3
```

`兼容性:` 全部

## for in 循环

```js
const obj = {name:'zhou',age:'**'}
for(let i in obj){
 console.log(i,obj[i])
}
// name zhou
// age **
```

`兼容性:` 全部

## Array.forEach() 循环

```js
const arr = [1,2,3];
arr.forEach(function(i,index){
 	console.log(i,index)
})
// 1 0
// 2 1
// 3 2
```

`是否可改变原数组：` ×

## Array.map() 循环

```js
let arr = [1,2,3];
let tt = arr.map(function(i){
 console.log(i)
 return i*2
})
// [2,4,6]
```

`是否可改变原数组：` ×

## Array.filter() 过滤

```js
const arr = [1,2,3];
const tt = arr.filter(function(i){
 	return i > 1
})
// [2,3]

```

`是否可改变原数组：` ×

## Array.some() 循环

```js
const arr = [1,2,3];
const tt = arr.some(function(i){
 	return i > 1
})
// true
```

`是否可改变原数组：` ×

**`some()`** 方法检测数组中是不是至少有 1 个元素通过了检测（提供的函数）。它返回的是一个 `Boolean` 类型的值。

**注意：some() 中只要有一项满足条件则返回 true**

## Array.every() 循环

```js
const arr = [1,2,3];
const tt = arr.every(function(i){
 	return i > 1
})
// false
```

`是否可改变原数组：` ×

`every()` 方法用于检测数组中的元素是否全部满足指定条件（函数提供）, 返回 `Boolean` 值，不改变原数组。
**注意：every() 中所有项满足条件 才会返回 true**

## Array.reduce() 循环

```js
const arr = [1, 2, 3, 4]
// accumulator 的初始值
const initValue = 0
const tt = arr.reduce(
  // accumulator: 上一次return的值
  (accumulator, currentValue) => accumulator + currentValue,
  initValue
);

console.log(tt)
// 10
```

**`reduce()`** 方法对数组中的每个元素按序执行一个由您提供的 **reducer** 函数，每一次运行 **reducer** 会将先前元素的计算结果作为参数传入，最后将其结果汇总为单个返回值。

第一次执行回调函数时，不存在“上一次的计算结果”。如果需要回调函数从数组索引为 0 的元素开始执行，则需要传递初始值。否则，数组索引为 0 的元素将被作为初始值 *initialValue*，迭代器将从第二个元素开始执行（索引为 1 而不是 0）。

## Array.reduceRight() 循环

```js
const arr = [[0, 1], [2, 3], [4, 5]]

const tt = arr.reduceRight((accumulator, currentValue) => accumulator.concat(currentValue));

console.log(tt)
// Array [4, 5, 2, 3, 0, 1]
```

**`reduceRight()`** 方法接受一个函数作为累加器（accumulator）和数组的每个值（从右到左）将其减少为单个值。

## for...of 循环

```js
const array1 = ['a', 'b', 'c'];

for (const element of array1) {
  console.log(element);
}

// "a"
// "b"
// "c"
```

